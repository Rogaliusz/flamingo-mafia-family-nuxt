<template>
  <div>
    <!-- Congrats my Friend! Good to se You - Don Flamingo -->
    <!-- Are You sure if You want go the darker cave, Romeo?-->
    <!-- No RiskNoFun, let's go deeper my friend... ?-->
    <Header></Header>

    <div id="content" class="content-container"><Nuxt></Nuxt>></div>
    <Footer />
  </div>
</template>
<script>
// @ is an alias to /src
import Web3EthContract from 'web3-eth-contract'
import AOS from 'aos'
import abi from '@/static/abi.json'
import Configuration from '@/static/configuration.json'
import 'aos/dist/aos.css' // You can also use <link> for styles

function detectMetaMask() {
  const { ethereum } = window
  return ethereum && ethereum.isMetaMask
}

const smartContract = new Web3EthContract(
  abi,
  Configuration.smartContractAddress
)

export default {
  name: 'Home',
  data: () => ({
    hasReveal: false,
  }),

  updated() {
    setTimeout(() => {
      AOS.init({
        duration: 1000,
      })
    }, 1000)
  },
  mounted() {
    setTimeout(() => {
      AOS.init({
        duration: 1000,
      })
    }, 1000)

    const { ethereum } = window
    Web3EthContract.setProvider(ethereum)
    const metaMaskinstalled = detectMetaMask()
    if (metaMaskinstalled) {
      console.log('MetaMask is installed!')
    } else {
      return
    }

    ethereum.on('chainChanged', () => {
      window.location.reload()
    })

    ethereum.on('accountsChanged', () => {
      window.location.reload()
    })

    this.loadData(this)
  },
  methods: {
    loadData: async (component) => {
      const { ethereum } = window
      await ethereum.enable()
      const accounts = await ethereum.request({
        method: 'eth_requestAccounts',
      })

      await smartContract.setProvider(ethereum)

      const nfts = await smartContract.methods
        .getMyTokensUri()
        .call({ from: accounts[0] })

      const collection = []

      if (nfts && nfts.length !== 0) {
        nfts.forEach((nft) => {
          const structure = {
            id: nft[0],
            url: nft[1],
            revelated: nft[2],
          }

          collection.push(structure)
        })

        component.hasReveal =
          collection.filter((x) => !x.revelated).length !== 0
      }

      component.$forceUpdate()
    },
  },
}
</script>

<style lang="scss">
html {
  scroll-behavior: smooth;
}

.content-container {
  max-width: 1265px;
  padding: 0 20px;
  margin: 0 auto;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

/* headers */

h2 {
  font-family: Pirata One;
  font-style: normal;
  font-weight: normal;
  font-size: 50px;
  line-height: 64px;
  width: 100%;
  color: #ffffff;
}

h3 {
  font-family: Teko;
  font-style: normal;
  font-weight: normal;
  font-size: 24px;
  line-height: 34px;
  margin: 0;

  color: #ffffff;
}
</style>
