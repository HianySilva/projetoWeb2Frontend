<template>
  <!-- Sidebar -->
  <nav class="sidebar" :class="{ active: sidebarVisible }" id="sidebar">
    <ul>
      <li><router-link to="/" @click="$emit('closeSidebar')"><i class="fas fa-home fa-2x"></i> Home</router-link></li>
      <li><router-link to="/view-room" @click="$emit('closeSidebar')"><i class="fas fa-door-open fa-2x"></i> Visualizar Salas</router-link></li>
      <li><router-link to="/view-lab" @click="$emit('closeSidebar')"><i class="fas fa-flask fa-2x"></i> Visualizar Laboratórios</router-link></li>
      <li id="addRoomMenu"><router-link to="/add-room" @click="$emit('closeSidebar')"><i class="fas fa-plus fa-2x"></i> Adicionar Sala</router-link></li>
      <li id="addLabMenu"><router-link to="/add-lab" @click="$emit('closeSidebar')"><i class="fas fa-plus fa-2x"></i> Adicionar Laboratório</router-link></li>
      <li id="loginMenu"><a href="#"><i class="fas fa-user-circle fa-2x"></i> Login</a></li>
      <li id="registerMenu"><a href="#"><i class="fas fa-user-plus fa-2x"></i> Cadastro</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    sidebarVisible: Boolean, // Recebe a propriedade para controlar a visibilidade
  },
};
</script>

<style scoped>
.sidebar {
  width: 250px;
  position: fixed;
  right: -250px;
  top: 0;
  height: 100%;
  background-color: #388e3c;
  transition: right 0.3s;
  z-index: 100;
  box-shadow: -2px 0 5px rgba(0, 0, 0, 0.5);
}

.sidebar.active {
  right: 0;
}

.sidebar ul {
  list-style-type: none;
  padding: 0;
}

.sidebar ul li {
  padding: 15px;
}

.sidebar ul li a {
  font-size: 1.3rem;
  color: white;
  text-decoration: none;
  display: flex;
  align-items: center;
  transition: background-color 0.3s;
}

.sidebar ul li a:hover {
  background-color: #4caf50;
}

.sidebar ul li a i {
  margin-right: 10px;
  color: white;
}
</style>
