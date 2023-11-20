<script setup>
import Home from './components/Home/Home/Home.vue';
import SideBar from './components/SideBar/SideBar.vue';
import NavBar from './components/NavBar/NavBar.vue';

</script>

<template>
  <div class="grid grid-cols-12">
    <div class="col-span-2 ">
      <SideBar></SideBar>
    </div>
    <div class="col-span-10">
      <Home></Home>
    </div>
  </div>
</template>

<style scoped></style>