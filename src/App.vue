<template>
  <router-view/>
  <nav>
    <router-link to="/"><i class="fa-solid fa-house-chimney"></i>Home</router-link>
    <router-link to="/ticket"><i class="fa-solid fa-ticket"></i>Ticket</router-link>
    <router-link to="/artist"><i class="fa-solid fa-user-group"></i>Artist</router-link>
    <router-link to="/profile"><i class="fa-solid fa-user"></i>Profile</router-link>
  </nav>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


nav {
  gap: 1em;
  display: flex;
  align-items: center;
  justify-content: center;

  width: 100%;
  color: var(--white);

  bottom: 0;
  position: fixed;

  height: 10vh;
  padding: 30px;
  background-color: var(--primary);
}

nav a {
  font-weight: bold;
  color: var(--white);
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
<script setup lang="ts">


</script>
