<template>
  <div v-show="!closed" class="white-paper">
    <h1>Flamingo Punks Are live!</h1>
    <h3>Mint Your own Flamingo Punk for a 5 Matic!</h3>
    <h3>
      <a class="medium" href=" https://flamingopunks.com/"
        >Check the Flamingo Punks website!</a
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
