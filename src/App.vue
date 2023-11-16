<script setup>
import Home from './components/Home/Home/Home.vue';
import SideBar from './components/SideBar/SideBar.vue';
import NavBar from './components/NavBar/NavBar.vue';

</script>

<template>
  <NavBar></NavBar>
  <div class="grid grid-cols-12 gap-4">
    <div class="col-span-3">
      <SideBar></SideBar>
    </div>
    <div class="col-span-9">
      <Home></Home>
    </div>
  </div>
</template>

<style scoped></style>
