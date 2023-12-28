<script setup>
import SideBar from './components/SideBar/SideBar.vue';
import NavBar from './components/NavBar/NavBar.vue';
import Home from './components/Home/Home.vue';
import bangladesh from '/data/bangladesh.json';
import { ref } from 'vue';

// ***************************
// all ref declare here 
// ***************************
const receivedDivision = ref(null);
const receivedDistrict = ref(null);
const countryInfo = ref(null);
const districtAddInfo = ref(null);

// ***************************
// emit declare here
// ***************************

const emit = defineEmits();

// ***************************
// reactive json file
// ***************************

countryInfo.value = bangladesh;
// districtAddInfo.value = bangladesh[0].division_information;
districtAddInfo.value = bangladesh;
console.log(districtAddInfo.value);



// console.log(bangladesh[0].division_name.toLowerCase());

// ***************************
// event handler declare here
// ***************************

const receiveDivisionDistrict = (divison, district) => {
  receivedDivision.value = divison;
  receivedDistrict.value = district;
};

const handleAddDivision = (newDivision) => {
  countryInfo.value.push(newDivision);
}

const handleAddDistrict = (newDistrict, match_division) => {
  // if(districtAddInfo.division_name)
  districtAddInfo.value.push(newDistrict);
  // console.log(match_division);
}

</script>

<template>
  <div class="grid lg:grid-cols-12 md:grid-cols-12 sm:grid-cols-12 ">
    <div class="lg:col-span-2 md:col-span-2 invisible md:visible lg:visible lg:relative md:relative mobile-view absolute">
      <SideBar
      :handleAddDistrict = "handleAddDistrict" 
      :countryInfo="countryInfo" 
      @sent-division-district="receiveDivisionDistrict"
      ></SideBar>
    </div>
    <div class="lg:col-span-10 md:col-span-10 sm:col-span-12">
      <NavBar></NavBar>
      <!-- Main Section -->
      <Home 
      :divisionInfo="receivedDivision" 
      :districtInfo="receivedDistrict" 
      @add-division="handleAddDivision"
      @add-district="handleAddDistrict"
      ></Home>
    </div>
  </div>
</template>

<style scoped></style>