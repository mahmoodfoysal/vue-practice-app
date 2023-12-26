<script setup>
import { toRefs, ref } from 'vue';
const props = defineProps({
    divisionInfo: {
        type: Object,
        default: null
    },
    districtInfo: {
        type: Object,
        default: null
    }
});

const { divisionInfo } = toRefs(props);
const { districtInfo } = toRefs(props);

// console.log("Info Division:", divisionInfo)
// console.log("Info District:", districtInfo)

const id = ref(null);
const person = ref('');
const age = ref(null);
const address = ref('');
const designation = ref('');
const url = ref('');
const district = ref('')
const formSubmitted = ref(false);
const inputData = ref([]);

const submitForm = () => {
    const submittedID = id.value;
    const submittedPerson = person.value;
    const submittedAge = age.value;
    const submittedAddress = address.value;
    const submittedDesignation = designation.value;
    const submittedUrl = url.value;
    const submittedDistrict = district.value;

    inputData.value.push({
    personID: submittedID,
    personName: submittedPerson,
    personAge: submittedAge,
    personAddress: submittedAddress,
    personDesignation: submittedDesignation,
    personImage: submittedUrl,
    personDistrict: submittedDistrict,
  });
  if (districtInfo.value) {
    districtInfo.value.info.push({
      id: submittedID,
      person: submittedPerson,
      age: submittedAge,
      address: submittedAddress,
      designation: submittedDesignation,
      image: submittedUrl,
      district: submittedDistrict,
    });
  }

    formSubmitted.value = true;
    id.value='';
    person.value='';
    age.value='';
    address.value='';
    designation.value='';
    url.value='';
    district.value='';
}

</script>
<template>
    <div>
        <section class="mb-2">
            <form @submit.prevent="submitForm">
                <div class="mx-4 grid gap-2 mb-4 md:grid-cols-2">
                    <div>
                        <label for="first_name"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">ID</label>
                        <input v-model.number="id" type="Number" id="first_name id-field'"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person ID" required>
                    </div>
                    <div>
                        <label for="last_name"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">Person</label>
                        <input v-model="person" type="text" id="last_name"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Full Name" required>
                    </div>
                    <div>
                        <label for="company"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">Age</label>
                        <input v-model.number="age" type="number" id="company"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Age" required>
                    </div>
                    <div>
                        <label for="phone"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">Address</label>
                            <input v-model="address" type="text" id="last_name"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Full Name" required>
                    </div>
                    <div>
                        <label for="website"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">Designation</label>
                        <input v-model="designation" type="text" id="website"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Designation" required>
                    </div>
                    <div>
                        <label for="visitors"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">Photo</label>
                        <input v-model="url" type="text" id="visitors"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Photo URL" required>
                    </div>
                    <div>
                        <label for="visitors"
                            class="block mb-1 text-sm font-medium text-gray-900 dark:text-white">District</label>
                        <input v-model="district" type="text" id="visitors"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person District" required>
                    </div>
                </div>
                <button type="submit"
                    class="mx-4 text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Submit</button>
            </form>
        </section>
        <!-- <h1 class="text-3xl text-center">Please select Your District</h1> -->
        <section class="main-container bg-[#F3F4F6] rounded-lg w-[100%] h-[100%] overflow-hidden">
            <div>
                <div class="flex justify-between border-b-2 border-#e2edfa py-[20px]">
                    <!-- <h4 class="text-2xl text-[#101833] mx-5 dashboard-text">Dashboard</h4>  -->
                    <h4 class="text-2xl text-[#101833] mx-5 dashboard-text">Division: {{ divisionInfo?.division_name }}</h4>
                    <h4 class="text-2xl text-[#101833] mx-5 dashboard-text">District: {{ districtInfo?.district_name }}</h4>

                </div>
            </div>

            <!-- table start -->

            <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
                <table class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400">
                    <thead 
                        class="text-xs text-gray-700 uppercase bg-[#F3F4F6] dark:bg-gray-700 dark:text-gray-400">
                        <tr>
                            <th scope="col" class="px-6 py-3">
                                ID
                            </th>
                            <th scope="col" class="px-6 py-3">
                                Person Name
                            </th>
                            <th scope="col" class="px-6 py-3">
                                Age
                            </th>
                            <th scope="col" class="px-6 py-3">
                                Address
                            </th>
                            <th scope="col" class="px-6 py-3">
                                Designation
                            </th>
                            <th scope="col" class="px-6 py-3">
                                Photo
                            </th>
                            <th scope="col" class="px-6 py-3">
                                District
                            </th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="disInfo in districtInfo?.info" :key="disInfo.id"
                            class="odd:bg-white odd:dark:bg-gray-900 even:bg-gray-50 even:dark:bg-gray-800 border-b dark:border-gray-700">
                            <th scope="row" class="px-6 py-2 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                                {{ disInfo.id }}
                            </th>
                            <td class="px-6 py-2">
                                {{ disInfo.person }}
                            </td>
                            <td class="px-6 py-2">
                                {{ disInfo.age }}
                            </td>
                            <td class="px-6 py-2">
                                {{ disInfo.address }}
                            </td>
                            <td class="px-6 py-2">
                                {{ disInfo.designation }}
                            </td>
                            <td class="px-6 py-2">
                                Dummy Photo
                            </td>
                            <td class="px-6 py-2">
                                {{ disInfo.district }}
                            </td>
                        </tr>

                        <!-- <tr v-if="formSubmitted" v-for="(givenInput, index) in inputData" :key="index"
                            class="odd:bg-white odd:dark:bg-gray-900 even:bg-gray-50 even:dark:bg-gray-800 border-b dark:border-gray-700">
                            <th scope="row" class="px-6 py-2 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                                {{ givenInput.personID }}
                            </th>
                            <td class="px-6 py-2">
                                {{givenInput.personName}}
                            </td>
                            <td class="px-6 py-2">
                                {{givenInput.personAge}}
                            </td>
                            <td class="px-6 py-2">
                                {{givenInput.personAddress}}
                            </td>
                            <td class="px-6 py-2">
                                {{ givenInput.personDesignation }}
                            </td>
                            <td class="px-6 py-2">
                                {{ givenInput.personImage }}
                            </td>
                            <td class="px-6 py-2">
                                {{givenInput.personDistrict}}
                            </td> 
                        </tr> -->
                    </tbody>
                </table>
            </div>

            <!-- table end -->

            <!-- value, user, ticket  -->
            <!-- dashboard features start -->

            <!-- <section class="flex gap-x-5 px-5 mt-5">
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10 h-16">
                <div>
                    <p class="text-xs text-[#D1D5DB] font-bold">VALUE</p>
                    <h6 class="text-sm text-[#596F92] font-semibold">$30,000</h6>
                </div>
                <span class="material-icons dollar-icon">
                    monetization_on
                </span>
            </div>
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10">
                <div>
                    <p class="text-xs text-[#D1D5DB] font-bold">USERS</p>
                    <h6 class="text-sm text-[#596F92] font-semibold">50,021</h6>
                </div>
                <span class="material-icons user-icon">
                    groups
                </span>
            </div>
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10">
                <div>
                    <p class="text-xs text-[#D1D5DB] font-bold">STOCK</p>
                    <h6 class="text-sm text-[#596F92] font-semibold">45021</h6>
                </div>
                <span class="material-icons stock-icon">
                    trending_up
                </span>
            </div>
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10">
                <div>
                    <p class="text-xs text-[#D1D5DB] font-bold">TICKET</p>
                    <h6 class="text-sm text-[#596F92] font-semibold">20516</h6>
                </div>
                <span class="material-icons ticket-icon">
                    confirmation_number
                </span>
            </div>
        </section> -->
            <!-- dashboard features end  -->

        </section>

    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Heebo&display=swap');

.dashboard-text {
    font-family: 'Heebo', sans-serif;
    font-weight: 500;
}

.main-container {
    box-shadow: 0px 0px 8px rgba(2, 108, 209, 0.1);
}

.dollar-icon {
    text-align: center;
    font-size: 30px;
    border-radius: 50%;
    border: none;
    background: gray;
    color: white;
    vertical-align: middle;
}

.user-icon {
    text-align: center;
    font-size: 30px;
    border-radius: 50%;
    /* border: 1px solid gray; */
    background: white;
    color: gray;
    vertical-align: middle;
}

.stock-icon {
    text-align: center;
    font-size: 30px;
    border-radius: 50%;
    /* border: 1px solid gray; */
    background: white;
    color: gray;
    vertical-align: middle;
}

.ticket-icon {
    text-align: center;
    font-size: 30px;
    background: white;
    color: gray;
    vertical-align: middle;
}
</style>


