<script setup>
import DashBoardHome from './DashBoardHome/DashBoardHome.vue';
import { toRefs } from 'vue';

// ********************************* 
// props declare here 
// ********************************* 
const props = defineProps({
    divisionInfo: {
        type: Object,
        default: null,
    },
    districtInfo: {
        type: Object,
        default: null,
    }
});

// ********************************* 
// all torefs declare here
// ********************************* 

const { divisionInfo } = toRefs(props);
const { districtInfo } = toRefs(props);

// ********************************* 
// emit declare here
// ********************************* 

const emit = defineEmits();

// ********************************* 
// all event handler declare here
// ********************************* 

const handleDivisionClick = (newDivision) => {
    emit('add-division', newDivision);
}

const handleDistrictClick = (newDistrict) => {
    emit('add-district', newDistrict);
}
</script>

<template>
    <div>
        <DashBoardHome 
        :divisionInfo="divisionInfo" 
        :districtInfo="districtInfo" 
        @add-division="handleDivisionClick"
        @add-district="handleDistrictClick"
        ></DashBoardHome>
    </div>
</template>
<style></style>