<template>
  <div id="header" class="header">
    <section id="nav" class="nav">
      <div v-if="!$device.isMobile" id="navbar" class="menu">
        <ul>
          <li><a href="/traits/">Traits</a></li>
          <li><a href="/#faq">FAQ</a></li>
          <li><a href="/#mint">Mint</a></li>
          <li><a href="/#roadmap">Roadmap</a></li>
          <li><a href="/#hierarchy">Hierarchy</a></li>
          <li><a href="/#fmf">About FMF</a></li>
        </ul>
      </div>

      <Burger
        v-if="$device.isMobile"
        style="padding-top: 15px; padding-left: 15px"
        @click.native="openSidebar()"
      ></Burger>

      <Sidebar ref="sidebar" class="sidebar" @click.native="closeSidebar()">
        <ul class="sidebar-panel-nav">
          <li><a href="/traits/">Traits</a></li>
          <li><a href="/#faq">FAQ</a></li>
          <li><a href="/#mint">Mint</a></li>
          <li><a href="/#roadmap">Roadmap</a></li>
          <li><a href="/#hierarchy">Hierarchy</a></li>
          <li><a href="/#fmf">About FMF</a></li>
        </ul>
      </Sidebar>
    </section>
  </div>
</template>

<script>
import Burger from './menu/Burger.vue'
import Sidebar from './menu/Sidebar.vue'

export default {
  name: 'FmfHeader',
  components: {
    Burger,
    Sidebar,
  },
  methods: {
    openSidebar() {
      this.$refs.sidebar.openSidebarPanel()
    },
    closeSidebar() {
      this.$refs.sidebar.closeSidebarPanel()
    },
  },
}
</script>

<style lang="scss" scoped>
@-moz-document url-prefix() {
  :root {
    --background: #e3a550;
  }
}

.sidebar {
  transition: transform 0.2s ease;
}

.header {
  background-color: #f7a234;
}

.nav {
  margin: auto;
  width: 1265px;
  height: 435px;
  background: #f7a234 url(@/static/assets/city.webp) center center no-repeat;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

.sidebar-panel-nav {
  display: flex;
  flex-direction: column-reverse;
}

.menu-item {
  position: absolute;
  font-family: Teko;
  font-style: normal;
  font-weight: normal;
  font-size: 20px;
  line-height: 29px;
  text-align: center;
  color: #000000;
}

@media only screen and (max-width: 768px) {
  .nav {
    background: #f7a234 url(@/static/assets/city.webp) center center no-repeat;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    width: 100%;
    height: 200px;
  }

  li {
    float: left;
  }
}

.main-nav {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0.8rem;
}

ul.sidebar-panel-nav {
  list-style-type: none;
}

ul.sidebar-panel-nav > li > a {
  color: #000;
  text-decoration: none;
  font-size: 1.5rem;
  display: block;
  padding-bottom: 0.5em;
}
</style>
