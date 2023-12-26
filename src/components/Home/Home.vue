<script setup>
import DashBoardHome from './DashBoardHome/DashBoardHome.vue';
import { toRefs } from 'vue';

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


const { divisionInfo } = toRefs(props);
const { districtInfo } = toRefs(props);


</script>

<template>
    <!-- <p v-if="divisionDistrictInfo === null"></p> -->
    <div>
        <DashBoardHome
        :divisionInfo="divisionInfo" 
        :districtInfo="districtInfo"
        ></DashBoardHome>
    </div>


<!-- {{ divisionDistrictInfo }} -->
</template>
<style>
</style>