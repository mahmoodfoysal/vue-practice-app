<script setup>
import SideBar from './components/SideBar/SideBar.vue';
import NavBar from './components/NavBar/NavBar.vue';
import Home from './components/Home/Home.vue';
import bangladesh from '/data/bangladesh.json';
import { ref } from 'vue';

// -------------------------------------all ref declare start ------------------------------------------------

const receivedDivision = ref(null);
const receivedDistrict = ref(null);
const countryInfo = ref(null);

// -------------------------------------all ref declare end ------------------------------------------------

// ------------------------------------- emit declare start ------------------------------------------------

const emit = defineEmits();

// ------------------------------------- emit declare end ------------------------------------------------

// -----------------------------------reactivate json file start ------------------------------------------------

countryInfo.value = bangladesh;

// -----------------------------------reactivate json file start ------------------------------------------------

// ---------------------------------all event handler declare here start ------------------------------------------- 

const receiveDivisionDistrict = (divison, district) => {
  receivedDivision.value = divison;
  receivedDistrict.value = district;
  // console.log("Division", divison, district)
};

const handleAddDivision = (newDivision) => {
  countryInfo.value = bangladesh;
  console.log("App Component Click", newDivision);

  countryInfo.value.push(newDivision);

}

// ---------------------------------all event handler declare here end ------------------------------------------- 

</script>

<template>
  <div class="grid lg:grid-cols-12 md:grid-cols-12 sm:grid-cols-12 ">
    <div class="lg:col-span-2 md:col-span-2 invisible md:visible lg:visible lg:relative md:relative mobile-view absolute">
      <SideBar :countryInfo="countryInfo" @sent-division-district="receiveDivisionDistrict"
        @add-division='handleAddDivision'></SideBar>
    </div>
    <div class="lg:col-span-10 md:col-span-10 sm:col-span-12">
      <NavBar></NavBar>
      <!-- Main Section -->
      <Home :divisionInfo="receivedDivision" :districtInfo="receivedDistrict" @add-division="handleAddDivision"></Home>
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