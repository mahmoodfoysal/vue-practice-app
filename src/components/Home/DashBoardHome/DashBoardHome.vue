<script setup>
import { toRefs } from 'vue';
const props = defineProps({
    divisionDistrictInfo: {
        type: Array,
        default: null
    },
});

const { divisionDistrictInfo } = toRefs(props)

</script>
<template>
    <div>
        <section class="mb-2" v-if="divisionDistrictInfo !== null">
            <form>
                <div class="mx-2 grid gap-6 mb-6 md:grid-cols-2">
                    <div>
                        <label for="first_name" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">ID</label>
                        <input type="Number" id="first_name"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person ID" required>
                    </div>
                    <div>
                        <label for="last_name" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Person</label>
                        <input type="text" id="last_name"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Full Name" required>
                    </div>
                    <div>
                        <label for="company"
                            class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Age</label>
                        <input type="number" id="company"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Age" required>
                    </div>
                    <div>
                        <label for="phone" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Address</label>
                        <input type="text" id="phone"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Full Address" pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}" required>
                    </div>
                    <div>
                        <label for="website" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Designation</label>
                        <input type="text" id="website"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Person Designation" required>
                    </div>
                    <div>
                        <label for="visitors" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Photo</label>
                        <input type="url" id="visitors"
                            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                            placeholder="Enter Photo URL">
                    </div>
                </div>
                <button type="submit"
                    class="mx-2 text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Submit</button>
            </form>

        </section>

        <h1 class="text-3xl text-center" v-if="divisionDistrictInfo === null">Please select Your District</h1>
        <section v-else class="main-container bg-[#F3F4F6] rounded-lg w-[100%] h-[100%] overflow-hidden">
            <div>
                <div class="flex justify-between border-b-2 border-#e2edfa py-[20px]">
                    <!-- <h4 class="text-2xl text-[#101833] mx-5 dashboard-text">Dashboard</h4>  -->
                    <h4 class="text-2xl text-[#101833] mx-5 dashboard-text">Division: {{
                        divisionDistrictInfo[0].division_name }}</h4>
                    <h4 class="text-2xl text-[#101833] mx-5 dashboard-text">District: {{
                        divisionDistrictInfo[1].district_name }}</h4>
                    <!-- <button
            data-modal-target="static-modal" data-modal-toggle="static-modal" 
            class="text-white bg-[#7C3AED] rounded-md px-[15px] mx-5 text-xs">Add New</button> -->


                </div>
            </div>


            <!-- table start -->


            <div class="relative overflow-x-auto shadow-md sm:rounded-lg">
                <table class="w-full text-sm text-left rtl:text-right text-gray-500 dark:text-gray-400">
                    <thead class="text-xs text-gray-700 uppercase bg-[#F3F4F6] dark:bg-gray-700 dark:text-gray-400">
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
                                Male
                            </th>
                            <th scope="col" class="px-6 py-3">
                                Female
                            </th>

                        </tr>
                    </thead>
                    <tbody v-for="districtInfo in divisionDistrictInfo">
                        <tr v-for="disInfo in districtInfo.info"
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
                                dummy
                            </td>
                            <td class="px-6 py-2">
                                dummy
                            </td>


                        </tr>



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

        <!-- modal start -->


        <!-- Modal toggle -->
        <!-- Main modal -->
        <div id="static-modal" data-modal-backdrop="static" tabindex="-1" aria-hidden="true"
            class="hidden overflow-y-auto overflow-x-hidden fixed top-0 right-0 left-0 z-50 justify-center items-center w-full md:inset-0 h-[calc(100%-1rem)] max-h-full">
            <div class="relative p-4 w-full max-w-2xl max-h-full">
                <!-- Modal content -->
                <div class="relative bg-white rounded-lg shadow dark:bg-gray-700">
                    <!-- Modal header -->
                    <div class="flex items-center justify-between p-4 md:p-5 border-b rounded-t dark:border-gray-600">
                        <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
                            Static modal
                        </h3>
                        <button type="button"
                            class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm w-8 h-8 ms-auto inline-flex justify-center items-center dark:hover:bg-gray-600 dark:hover:text-white"
                            data-modal-hide="static-modal">
                            <svg class="w-3 h-3" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none"
                                viewBox="0 0 14 14">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="m1 1 6 6m0 0 6 6M7 7l6-6M7 7l-6 6" />
                            </svg>
                            <span class="sr-only">Close modal</span>
                        </button>
                    </div>
                    <!-- Modal body -->
                    <div class="p-4 md:p-5 space-y-4">
                        <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
                            With less than a month to go before the European Union enacts new consumer privacy laws for its
                            citizens, companies around the world are updating their terms of service agreements to comply.
                        </p>
                        <p class="text-base leading-relaxed text-gray-500 dark:text-gray-400">
                            The European Union’s General Data Protection Regulation (G.D.P.R.) goes into effect on May 25
                            and is meant to ensure a common set of data rights in the European Union. It requires
                            organizations to notify users as soon as possible of high-risk data breaches that could
                            personally affect them.
                        </p>
                    </div>
                    <!-- Modal footer -->
                    <div class="flex items-center p-4 md:p-5 border-t border-gray-200 rounded-b dark:border-gray-600">
                        <button data-modal-hide="static-modal" type="button"
                            class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">I
                            accept</button>
                        <button data-modal-hide="static-modal" type="button"
                            class="ms-3 text-gray-500 bg-white hover:bg-gray-100 focus:ring-4 focus:outline-none focus:ring-blue-300 rounded-lg border border-gray-200 text-sm font-medium px-5 py-2.5 hover:text-gray-900 focus:z-10 dark:bg-gray-700 dark:text-gray-300 dark:border-gray-500 dark:hover:text-white dark:hover:bg-gray-600 dark:focus:ring-gray-600">Decline</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- modal end -->

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
}</style>


