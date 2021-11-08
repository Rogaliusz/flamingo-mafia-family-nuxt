<template>
  <div id="mint" class="minting-section">
    <h2 data-aos="fade-up" data-aos-duration="1000">Mint</h2>
    <div class="minting-container">
      <div class="minting-gateway-container">
        <img
          class="minting-gateway"
          data-aos="fade-left"
          data-aos-duration="1000"
          src="@/static/assets/eggs.webp"
          width="300"
          height="300"
        />
      </div>
      <div class="minting-desc" data-aos="fade-right" data-aos-duration="1000">
        <h2>Why is it worth being part of the Flamingo Mafia Family?</h2>
        <h3>1. Every Flamingo egg can be revealed by its holder.</h3>
        <h3>
          2. 100 Random flamingo holders get 25% of the secondary sales fees
          collected on OpenSea.
        </h3>
        <h3>3. Egg airdrops for the Flamingo Mafia Family community.</h3>
        <h3>
          4. Holding Flamingos grants you 100% creative and commercial rights.
        </h3>
        <h3>
          5. Flamingos are built on the Polygon Network so gas fees are
          incredibly small!
        </h3>
      </div>
    </div>
    <div
      v-show="!connected"
      class="mint-form"
      data-aos-duration="1000"
      data-aos="fade-up"
    >
      <button
        class="minting-button"
        style="width: 100%"
        @click="connectToMetamask()"
      >
        <h3 style="width: 100%; margin: 20px 0px">Connect to a Metamask</h3>
      </button>
    </div>
    <div v-show="connected">
      <div class="mint-form" data-aos="fade-up" data-aos-duration="1000">
        <div v-show="invalidNetwork == true" style="margin: 20px 0px">
          <h3>Flamingo Mafia Family is built on Matic Polygon Network!</h3>
          <h3>
            To mint it, please change Metamask network to polygon (137) -
            (https://polygon-rpc.com/).
          </h3>
          <h3>We recommend use the Chrome browser on Your pc.</h3>
          <h3 style="margin-top: 5px">
            <a
              class="mint-link"
              href="https://support.opensea.io/hc/en-us/articles/1500011368842-How-can-I-switch-my-wallet-to-blockchains-like-Polygon-"
              >Click here to check how to do this</a
            >
          </h3>
        </div>
        <div v-show="invalidNetwork == false">
          <div style="margin-top: 10px">
            <h3>Minted: {{ minted }} / {{ total }}</h3>

            <div class="minting-eth">
              <button class="minting-count-btn" @click="decrease()">
                <h3>-</h3>
              </button>
              <h3>{{ count }}</h3>
              <button class="minting-count-btn" @click="inrecease()">
                <h3>+</h3>
              </button>
            </div>
          </div>
          <button class="minting-button" @click="click()">
            <h3 style="width: 100%">
              Mint ({{ (count * (cost / 1000000000000000000)).toFixed(2) }}
              MATIC)
              {{ error }}
            </h3>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Web3EthContract from 'web3-eth-contract'
import Configuration from '@/static/configuration.json'
import abi from '@/static/abi.json'

export default {
  name: 'FmfMinting',
  data: () => ({
    count: 0,
    minted: 0,
    total: 0,
    cost: 0,
    error: '',
    invalidNetwork: true,
    smartContract: undefined,
    connected: false,
  }),
  computed: {},
  async mounted() {
    try {
      const { ethereum } = window
      Web3EthContract.setProvider(ethereum)
      this.smartContract = new Web3EthContract(
        abi,
        Configuration.smartContractAddress
      )

      const accounts = await ethereum.request({
        method: 'eth_requestAccounts',
      })

      this.connected = accounts.length !== 0
      if (!this.connected) {
        return
      }

      await this.checkNetwork(ethereum)
      await this.refreshData()
    } catch (exception) {}
  },
  methods: {
    async connectToMetamask() {
      try {
        const { ethereum } = window
        Web3EthContract.setProvider(ethereum)
        this.smartContract = new Web3EthContract(
          abi,
          Configuration.smartContractAddress
        )
        await ethereum.request({
          method: 'eth_requestAccounts',
        })
      } catch (exception) {}
    },
    async refreshData() {
      this.total = await this.smartContract.methods.maxSupply().call()
      this.minted = await this.smartContract.methods.totalSupply().call()
      this.cost = await this.smartContract.methods.cost().call()

      this.$forceUpdate()
    },
    async checkNetwork(ethereum) {
      const networkId = await ethereum.request({
        method: 'net_version',
      })

      // eslint-disable-next-line eqeqeq
      this.invalidNetwork = networkId != Configuration.network

      this.$forceUpdate()
    },
    async click() {
      const { ethereum } = window
      const accounts = await ethereum.request({
        method: 'eth_requestAccounts',
      })

      const address = accounts[0]
      const calculatedCost = this.cost * this.count

      this.smartContract.methods
        .mint(address, this.count)
        .send({ from: address, value: calculatedCost })
        .on('recipt', () => window.reload())

      this.error = '- miniting...'
    },
    inrecease() {
      if (this.count !== 20) {
        this.count++
      }
    },
    decrease() {
      if (this.count !== 0) {
        this.count--
      }
    },
  },
}
</script>
<style>
.mint-link {
  text-decoration: none;
  color: #fff;
}

.minting-count-btn {
  cursor: pointer;
  text-align: center;
  display: flex;
  flex-direction: column;
  border: none;
  background-color: #1a1a1b;
  padding: 0px 15px;
}

.minting-count-btn:hover > h3 {
  color: #f7a234;
}

.minting-eth {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 10px;
  margin-top: 20px;
}
.minting-container {
  display: flex;
  flex-direction: row;
  gap: 30px;
}

.minting-section {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.mint-form {
  border: 2px solid white;
  border-style: solid;
  background-color: #1a1a1b;
}

.mint-form:hover {
  transform: scale(1.2) !important;
}

.minting-gateway-container-title > h2 {
  text-align: left;
  line-height: 0%;
}
.minting-gateway-container-title {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.minting-gateway-container {
  display: flex;
  justify-content: center;
}

.minting-desc {
  display: flex;
  flex-direction: column;
  padding: 0px 20px;
}

.minting-desc > h2 {
  color: #f7a234;
  font-size: 40px;
  text-align: start;
  margin-top: 0px;
}

.minting-desc > h3 {
  text-align: start;
  line-height: 40px;
}

.minting-gateway {
  display: flex;
  flex-direction: column;
  gap: 20px;
  justify-content: center;
  border: 2px solid white;
  border-style: solid;
  background-color: #1a1a1b;
}

.minting-button {
  cursor: pointer;
  padding: 30px;
  text-align: center;
  display: flex;
  flex-direction: column;
  border: none;
  gap: 30px;
  background-color: #1a1a1b;
  width: 100%;
  padding-top: 20px;

  transition: all 0.5s linear;
  transition: width 1s ease-in-out;
}

.minting-button:hover h3 {
  color: #f7a234 !important;
}

@media only screen and (max-width: 768px) {
  .minting-desc > h2 {
    text-align: center;
  }

  .minting-desc > h3 {
    text-align: center;
    margin-bottom: 10px;
  }

  .minting-container {
    flex-direction: column;
  }
}
</style>
