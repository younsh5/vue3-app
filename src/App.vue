<template>
  <div id="app">
    <Header @toggle="toggleSidebar" />
    <Sidebar :active="sidebarActive" />
    <div class="content" :class="contentClass">
    <router-view />
      <router-view />
      <router-view />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Sidebar from "./components/Sidebar.vue";

export default {
  components: {
    Header,
    Sidebar
  },
  data() {
    return {
      sidebarActive: true
    };
  },
  computed: {
    contentClass() {
      return this.sidebarActive ? "content-with-sidebar" : "full-content";
    }
  },
  methods: {
    toggleSidebar() {
      this.sidebarActive = !this.sidebarActive;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
}

.content-with-sidebar {
  margin-left: 225px;
}

.full-content {
  margin-left: 0;
}

.content {
  display: flex;
  transition: all 0.3s;
  background-color: white;
  width: 800px;
}
</style>
