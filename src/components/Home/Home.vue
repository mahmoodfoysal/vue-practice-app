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
    },
    divisionClickInfo: {
        type: String,
        default: null,
    }
});

// ********************************* 
// all torefs declare here
// ********************************* 

const { divisionInfo } = toRefs(props);
const { districtInfo } = toRefs(props);
const {divisionClickInfo} = toRefs(props);

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

const handleDistrictClick = (newDistrict, match_division) => {
    emit('add-district', newDistrict, match_division);
}

const handleEmpDelete = (div, dis, id) => {
    emit('handle-emp-delete', div, dis, id)
}

const handleUpdateEmpInfo = (divInfo, disInfo, empInfo, updateInfo) => {
    emit('handle-edit-emp-info', divInfo, disInfo, empInfo, updateInfo);
}
</script>

<template>
    <div>
        <DashBoardHome 
        :divisionInfo="divisionInfo" 
        :districtInfo="districtInfo" 
        :divisionClickInfo="divisionClickInfo"
        @add-division="handleDivisionClick"
        @add-district="handleDistrictClick"
        @handle-emp-delete="handleEmpDelete"
        @handle-edit-emp-info="handleUpdateEmpInfo"
        ></DashBoardHome>
    </div>
</template>
<style></style>