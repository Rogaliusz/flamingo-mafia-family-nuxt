<template>
  <div id="header" class="header">
    <section>
      <div id="nav" class="nav">
        <div class="logo-section">
          <div v-show="$device.isMobile">
            <Burger
              style="padding-left: 20px"
              v-show="$device.isMobile"
              @click.native="openSidebar()"
            ></Burger>

            <Sidebar
              ref="sidebar"
              class="sidebar"
              @click.native="closeSidebar()"
            >
              <ul class="sidebar-panel-nav">
                <li><a href="/traits/">Traits</a></li>
                <li><a href="/#faq">FAQ</a></li>
                <li><a href="/#mint">Mint</a></li>
                <li><a href="/#roadmap">Roadmap</a></li>
                <li><a href="/#hierarchy">Hierarchy</a></li>
                <li><a href="/#fmf">About FMF</a></li>
              </ul>
            </Sidebar>
          </div>
          <h1>Flamingo Mafia Family</h1>
        </div>
        <div v-show="!$device.isMobile" id="navbar" class="menu">
          <ul>
            <li><a href="/traits/">Traits</a></li>
            <li><a href="/#faq">FAQ</a></li>
            <li><a href="/#mint">Mint</a></li>
            <li><a href="/#roadmap">Roadmap</a></li>
            <li><a href="/#hierarchy">Hierarchy</a></li>
            <li><a href="/#fmf">About FMF</a></li>
          </ul>
        </div>
      </div>
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
.logo-section {
  display: flex;
  flex-direction: row;
  gap: 20px;
  justify-content: space-around;
  align-items: center;
}

.logo-img {
  background: radial-gradient(
    50% 50% at 50% 50%,
    #f7a234 0%,
    rgba(255, 255, 255, 0.734375) 0.01%,
    rgba(252, 252, 252, 0.726798) 0.02%,
    $primary-bk 100%
  );

  display: block;
  margin-left: auto;
  margin-right: auto;
}
.sidebar {
  transition: transform 0.2s ease;
}

.header {
  background-color: $primary-bk;
  border-bottom: 2px solid white;
}

.nav {
  max-width: $width;
  margin: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
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
  color: #fff;
}

a {
  color: #fff;
}

.logo-section > h1 {
  margin-left: 20px;
}

@media only screen and (max-width: 768px) {
  li {
    float: left;
  }

  .logo-section {
    width: 100%;
  }

  .logo-section > h1 {
    text-align: center;
    width: 100%;
    font-size: 32px;
    margin: 0px;
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
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem;
  display: block;
  padding-bottom: 0.5em;
}
</style>
