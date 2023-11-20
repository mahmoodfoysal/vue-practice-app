<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Heebo&display=swap');
.layout-sidebar {
    height: 562px;
    background-color: transparent;
}

.deviation-list {
    border-right: 1px solid #e2edfa;
}
.sub-menu li{
    margin: 10px 0;
    color: #B0C6D4;
    cursor: pointer;
}
.font-side {
    font-family: 'Heebo', sans-serif;
    font-size: 14px;
}
</style>
<template>
    <section class="layout-sidebar deviation-list w-[100%] px-2 pt-[5px]">
        <div id="accordion-collapse" data-accordion="collapse">
            <h2 id="accordion-collapse-heading-1">
                <button type="button"
                    class="flex items-center justify-between w-full p-2 font-medium rtl:text-right text-gray-500   border-gray-200 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 focus:rounded-[12px] dark:hover:bg-gray-800 gap-3"
                    data-accordion-target="#accordion-collapse-body-1" aria-expanded="false"
                    aria-controls="accordion-collapse-body-1">
                    <span class="text-[#8E949F] font-side">Dashboard</span>
                    <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M9 5 5 1 1 5" />
                    </svg>
                </button>
            </h2>
            <div id="accordion-collapse-body-1" class="hidden" aria-labelledby="accordion-collapse-heading-1">
                <div class="p-2 dark:border-gray-700 dark:bg-gray-900">

                    <ul class="sub-menu font-side">
                        <li>Default</li>
                        <li>Project Management</li>
                    </ul>
                </div>
            </div>
            <h2 id="accordion-collapse-heading-2">
                <button type="button"
                    class="flex items-center justify-between w-full p-2 font-medium rtl:text-right text-gray-500 border-gray-200 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 focus:rounded-[12px] dark:hover:bg-gray-800 gap-3"
                    data-accordion-target="#accordion-collapse-body-2" aria-expanded="false"
                    aria-controls="accordion-collapse-body-2">
                    <span class="text-[#8E949F] font-side">Dhaka</span>
                    <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M9 5 5 1 1 5" />
                    </svg>
                </button>
            </h2>
            <div id="accordion-collapse-body-2" class="hidden" aria-labelledby="accordion-collapse-heading-2">
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
            </div>
            <h2 id="accordion-collapse-heading-3">
                <button type="button"
                    class="flex items-center justify-between w-full p-2 font-medium rtl:text-right text-gray-500 border-gray-200 focus:ring-gray-200 dark:focus:ring-gray-800 dark:border-gray-700 dark:text-gray-400 hover:bg-gray-100 focus:rounded-[12px] dark:hover:bg-gray-800 gap-3"
                    data-accordion-target="#accordion-collapse-body-3" aria-expanded="false"
                    aria-controls="accordion-collapse-body-3">
                    <span class="text-[#8E949F] font-side">Rajshahi</span>
                    <svg data-accordion-icon class="w-3 h-3 rotate-180 shrink-0" aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M9 5 5 1 1 5" />
                    </svg>
                </button>
            </h2>
            <div id="accordion-collapse-body-3" class="hidden" aria-labelledby="accordion-collapse-heading-3">
                <div class="p-2 dark:border-gray-700 dark:bg-gray-900">

                    <ul class="sub-menu font-side">
                        <li>Rajshahi</li>
                        <li>Noagoan</li>
                        <li>Chapai Nababgonje</li>
                        <li>Nator</li>
                        <li>Bogura</li>
                        <li>Joypurhat</li>
                    </ul>
                </div>
            </div>
        </div>



    </section>
</template>

<script setup>

</script>
