<script setup>
import DashBoardHome from './DashBoardHome/DashBoardHome.vue';
import { toRefs } from 'vue';

const props = defineProps({
    divisionDistrictInfo: {
        type: Array,
        default: null,
    }
    
});

const { divisionDistrictInfo } = toRefs(props)
// console.log(divisionDistrictInfo)


</script>

<template>
<DashBoardHome :district="divisionDistrictInfo"></DashBoardHome>

<!-- {{ divisionDistrictInfo }} -->
</template>
<style>
</style>