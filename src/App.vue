<script setup>
import NavBar from './components/NavBar/NavBar.vue';
import SideBar from './components/SideBar/SideBar.vue';
import Home from './components/Home/Home.vue';
import bangladesh from '/data/bangladesh.json';
import { ref } from 'vue';

// ***************************
// all ref declare here 
// ***************************
const receivedDivision = ref(null);
const receivedDistrict = ref(null);
const receivedClickDiv = ref(null);
const receivedDistrictInput = ref(null)
const countryInfo = ref(null);

// ***************************
// emit declare here
// ***************************

const emit = defineEmits();

// ***************************
// reactive json file
// ***************************

countryInfo.value = bangladesh;

// ***************************
// event handler declare here
// ***************************

// event handler for division and district information from sidebar props 
const receiveDivisionDistrict = (divison, district) => {
  receivedDivision.value = divison;
  receivedDistrict.value = district;
};

// event handler for division information string from sidebar 
const receivedClickDivision = (div) => {
  receivedClickDiv.value = div;
}

// event handler for push division for main array 
const handleAddDivision = (newDivision) => {
  countryInfo.value.push({
    div_id: newDivision.div_id,
    division_name: newDivision.division_name,
    division_information: []
  });
}

// event handler for push district main array 
const handleAddDistrict = (newDistrict, match_division) => {
  const division = countryInfo.value.find(div => div.div_id === match_division.div_id);
  if (division) {
    const district = division?.division_information;
    receivedDistrictInput.value = district;
    // const divisionInformation = ref(division ? division.division_information : null);
    console.log(district);
    if (receivedDistrictInput.value) {
      receivedDistrictInput.value.push({
        dis_id: newDistrict.dis_id,
        district_name: newDistrict.district_name,
        info: [],
      });

    }
    else {
      console.log(`Division information not found for division with ID:`);
    }
  }
};

const handleEmpDelete = (div, dis, empid) => {
  const division = countryInfo.value.find(divi => divi.division_name === div);
  if (division) {
    const district = division.division_information.find(dist => dist.district_name === dis);
    if (district) {
      const EmployeeRemove = district.info.findIndex(person => person.id === empid);
      if (EmployeeRemove !== -1) {
        if ((confirm("Are you sure! Want to delete employee?") == true)) {
          district.info.splice(EmployeeRemove, 1);
        }
      }
    }
  }
}

</script>

<template>
  <div class="grid lg:grid-cols-12 md:grid-cols-12 sm:grid-cols-12 ">
    <div class="lg:col-span-2 md:col-span-2 invisible md:visible lg:visible lg:relative md:relative mobile-view absolute">
      <SideBar :handleAddDistrict="handleAddDistrict" :countryInfo="countryInfo"
        @sent-division-district="receiveDivisionDistrict" @sent-division="receivedClickDivision"></SideBar>
    </div>
    <div class="lg:col-span-10 md:col-span-10 sm:col-span-12">
      <NavBar></NavBar>
      <!-- Main Section -->
      <Home :divisionInfo="receivedDivision" :districtInfo="receivedDistrict" :divisionClickInfo="receivedClickDiv"
        @add-division="handleAddDivision" @add-district="handleAddDistrict" @handle-emp-delete="handleEmpDelete"></Home>
    </div>
  </div>
</template>

<style scoped></style>