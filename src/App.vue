<script setup>
import { RouterLink, RouterView } from 'vue-router'
import UserList from './components/UserList.vue';
import UserForm from './components/UserForm.vue';
</script>

<template>
  <header>
    <div class="home">
      <UserForm/>
      <UserList/>
    </div>
      <!-- <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav> -->
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  display: flex;
  justify-content: center;
}
.home{
  width: 592px;
  display: flex;
  flex-direction: column;
  row-gap: 20px;
}
</style>
