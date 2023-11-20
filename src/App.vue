<script setup>
import SideBar from './components/SideBar/SideBar.vue';
import NavBar from './components/NavBar/NavBar.vue';
import Home from './components/Home/Home.vue';

</script>

<template>
  <div class="grid grid-cols-12">
    <div class="col-span-2">
      <SideBar></SideBar>
    </div>
    <div class="col-span-10">
      <NavBar></NavBar>
      <!-- Main Section -->
      <Home></Home>
    </div>
  </div>
</template>

<style scoped></style>