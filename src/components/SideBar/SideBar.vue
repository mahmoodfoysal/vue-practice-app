<script setup>
import { toRefs, defineEmits, ref } from 'vue';
const props = defineProps({
    countryInfo: {
        type: Array,
        default: null
    }
});

const isBackgroundActive = ref(false);
const { countryInfo } = toRefs(props)
const emit = defineEmits();
const handleDistrictIfo = (division, district) => {

    emit('sent-district', [division, district])
    isBackgroundActive.value = !isBackgroundActive.value;
    // console.log('Division', division);
    // console.log('District', district);
}
</script>
<template>
    <section class="layout-sidebar deviation-list w-[100%] px-2 pt-[5px]">
        <div id="accordion-collapse" data-accordion="collapse">
            <div v-for="division in countryInfo" :key="division.div_id">
                <h2 :id="`accordion-collapse-heading-${division.div_id}`">
                    <button type="button"
                        class="flex items-center justify-between w-full p-2 font-medium rtl:text-right text-gray-500   border-gray-200 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 focus:rounded-[12px] dark:hover:bg-gray-800 gap-3"
                        :data-accordion-target="`#accordion-collapse-body-${division.div_id}`" aria-expanded="false"
                        :aria-controls="`accordion-collapse-body-${division.div_id}`">
                        <span class="text-[#8E949F] font-side">{{ division.division_name }}</span>
                        <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true"
                            xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M9 5 5 1 1 5" />
                        </svg>
                    </button>
                </h2>

                <div :id="`accordion-collapse-body-${division.div_id}`" class="hidden"
                    :aria-labelledby="`accordion-collapse-heading-${division.div_id}`">
                    <div class="p-2 dark:border-gray-700 dark:bg-gray-900">

                        <ul v-for="district in division?.division_information" :key="district.dis_id"
                            class="sub-menu font-side">
                            <li @click="handleDistrictIfo(division, district)"
                                :class="{ 'bg-blue-700': isBackgroundActive }">
                                {{ district.district_name }}
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
            <!-- <h2 id="accordion-collapse-heading-2">
                <button type="button"
                    class="flex items-center justify-between w-full p-2 font-medium rtl:text-right text-gray-500 border-gray-200 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 focus:rounded-[12px] dark:hover:bg-gray-800 gap-3"
                    data-accordion-target="#accordion-collapse-body-2" aria-expanded="false"
                    aria-controls="accordion-collapse-body-2">
                    <span class="text-[#8E949F] font-side">Dummy Dhaka</span>
                    <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M9 5 5 1 1 5" />
                    </svg>
                </button>
            </h2> -->
            <!-- <div id="accordion-collapse-body-2" class="hidden" aria-labelledby="accordion-collapse-heading-2">
                <div class="p-2 dark:border-gray-700 dark:bg-gray-900">

                    <ul class="sub-menu font-side">
                        <li>Dhaka</li>
                        <li>Manikganj </li>
                        <li>Gazipiur</li>
                        <li>Tangail</li>
                        <li>Madaripur</li>
                        <li>Narayanganj</li>
                        <li>Narsingdi</li>
                    </ul>
                </div>
            </div> -->
        </div>
    </section>
</template>



<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Heebo&display=swap');

.layout-sidebar {
    height: 562px;
    background-color: transparent;
}

.deviation-list {
    border-right: 1px solid #e2edfa;
}

.sub-menu li {
    margin: 10px 0;
    color: #B0C6D4;
    cursor: pointer;
}

.font-side {
    font-family: 'Heebo', sans-serif;
    font-size: 14px;
}</style>
