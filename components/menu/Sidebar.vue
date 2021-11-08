<template>
  <div class="sidebar">
    <div
      class="sidebar-backdrop"
      @click="closeSidebarPanel"
      v-show="isPanelOpen"
    ></div>
    <transition name="slide">
      <div v-show="isPanelOpen" class="sidebar-panel">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data: () => ({
    isPanelOpen: false,
  }),
  methods: {
    closeSidebarPanel() {
      this.isPanelOpen = false
    },
    openSidebarPanel() {
      this.isPanelOpen = true
    },
  },
}
</script>
<style>
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.2s ease;
}

.slide-enter,
.slide-leave-to {
  transform: translateX(-100%);
  transition: all 150ms ease-in 0s;
}

.sidebar-backdrop {
  background-color: rgba(0, 0, 0, 0.5);
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  cursor: pointer;
}

.sidebar-panel {
  overflow-y: auto;
  background-color: #f7a234;
  position: fixed;
  left: 0;
  top: 0;
  height: 100vh;
  z-index: 999;
  padding: 10px 20px 2rem 20px;
  width: 150px;
}
</style>
