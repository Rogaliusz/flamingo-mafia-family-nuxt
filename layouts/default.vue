<template>
  <div>
    <!-- Congrats my Friend! Good to se You - Don Flamingo -->
    <!-- Are You sure if You want go the darker cave, Romeo?-->
    <!-- No RiskNoFun, let's go deeper my friend... ?-->
    <HeaderNew></HeaderNew>

    <div id="content" class="content-container"><Nuxt></Nuxt></div>
    <Footer />
    <WhiteNews class="news"></WhiteNews>
  </div>
</template>
<script>
// @ is an alias to /src
import AOS from 'aos'
import 'aos/dist/aos.css' // You can also use <link> for styles

export default {
  name: 'Home',
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
  },
}
</script>

<style lang="scss">
html {
  scroll-behavior: smooth;
}

.content-container {
  max-width: $width;
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

.news {
  bottom: 0;
  margin: auto;
  width: 100%;
  position: fixed;
  height: auto;
}
</style>
