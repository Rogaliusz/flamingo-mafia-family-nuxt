<template>
  <div v-show="!closed" class="white-paper">
    <h1>Flamingo Punks Airdrop!</h1>
    <h3>
      Every Flamingo Holder at 22 November 2021 will receive a free Flamingo
      Punk!
    </h3>
    <h3>
      <a
        class="medium"
        href=" https://flamingomafiafamily.medium.com/flamingo-punks-1st-flamingo-mafia-family-extension-a6ab9e193590"
        >Check the Medium article to get a more info!</a
      >
    </h3>
    <br />
    <h3 class="close" @click="close()">[Close]</h3>
    <br />
  </div>
</template>
<script>
export default {
  data: () => ({
    closed: false,
  }),
  methods: {
    close() {
      this.closed = true
      this.$forceUpdate()
      this.$gtm.push({ event: 'close-news' })
    },
  },
}
</script>
<style lang="scss">
.white-paper {
  background-color: white;
  border-top: 2px solid darkred;
  border-top-style: solid;
}

.white-paper > h1 {
  color: darkred;
}

.white-paper > h3 {
  color: black;
}

.white-paper > h3 > .medium {
  color: black;
}

.white-paper > h3:hover > .medium {
  color: darkred;
}

.close {
  cursor: pointer;
}

.close:hover {
  color: darkred;
  cursor: pointer;
}
</style>
