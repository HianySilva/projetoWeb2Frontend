<template>
  <div class="main-layout">
    <Header @toggleSidebar="toggleSidebar" />
    <Sidebar :sidebarVisible="sidebarVisible" @closeSidebar="toggleSidebar" />
    <main>
      <router-view></router-view>
      <!-- Aqui as páginas serão renderizadas -->
    </main>
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Sidebar from "../components/Sidebar.vue";

export default {
  components: {
    Header,
    Sidebar,
  },
  data() {
    return {
      sidebarVisible: false, // Controle da visibilidade da Sidebar
    };
  },
  methods: {
    toggleSidebar() {
      this.sidebarVisible = !this.sidebarVisible; // Alterna a visibilidade da Sidebar
    },
    closeSidebar() {
      this.sidebarVisible = false; // Fecha a sidebar
    }
  },
};
</script>

<style scoped>
.main-layout {
  display: flex;
  flex-direction: column;
}
</style>
