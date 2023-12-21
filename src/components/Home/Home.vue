<script setup>
import DashBoardHome from './DashBoardHome/DashBoardHome.vue';
import { toRefs } from 'vue';

const props = defineProps({
    divisionDistrictInfo: {
        type: Array,
        default: null,
    }
    
});

const { divisionDistrictInfo } = toRefs(props);


</script>

<template>
    <!-- <p v-if="divisionDistrictInfo === null"></p> -->
    <div>
        <DashBoardHome :divisionDistrictInfo="divisionDistrictInfo" ></DashBoardHome>
    </div>


<!-- {{ divisionDistrictInfo }} -->
</template>
<style>
</style>