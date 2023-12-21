<script setup>
import SideBar from './components/SideBar/SideBar.vue';
import NavBar from './components/NavBar/NavBar.vue';
import Home from './components/Home/Home.vue';
import bangladesh from '/data/bangladesh.json';
import { ref } from 'vue';

const receivedData = ref(null);

const receiveData = (data) => {
  receivedData.value = data;
  console.log("Result", data)
};


</script>

<template>
  <div class="grid lg:grid-cols-12 md:grid-cols-12 sm:grid-cols-12 ">
    <div class="lg:col-span-2 md:col-span-2 invisible md:visible lg:visible lg:relative md:relative mobile-view absolute">
      <SideBar :countryInfo="bangladesh" @sent-information="receiveData"></SideBar>
    </div>
    <div class="lg:col-span-10 md:col-span-10 sm:col-span-12">
      <NavBar></NavBar>
      <!-- Main Section -->
      <Home :divisionDistrictInfo = "receivedData"></Home>
    </div>
  </div>
</template>

<style scoped>
@media only screen and (max-width: 600px) {
  /* .mobile-view {
    visibility: hidden;
    position: absolute;
  } */
}
</style>