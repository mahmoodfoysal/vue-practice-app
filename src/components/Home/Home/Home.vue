<style scoped>
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
<template>
    <section class="main-container bg-[#f3f3f3] rounded-lg py-2 w-[98%] h-[100%] overflow-hidden">
        <div class="flex justify-between border-b-2 border-#e2edfa pb-3">
            <h4 class="text-2xl decoration-gray-900 mx-5">Deshboard</h4>
            <button class="text-white bg-violet-700 rounded p-2 mx-5">Go To Website</button>
        </div>

        <!-- value, user, ticket  -->
        <section class="flex gap-x-5 px-5 mt-5">
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10 h-16">
                <div>
                    <p class="text-xs">Value</p>
                    <h6 class="text-sm">$30,000</h6>
                </div>
                <span class="material-icons dollar-icon">
                    monetization_on
                </span>
            </div>
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10">
                <div>
                    <p class="text-xs">Users</p>
                    <h6 class="text-sm">50,021</h6>
                </div>
                <span class="material-icons user-icon">
                    groups
                </span>
            </div>
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10">
                <div>
                    <p class="text-xs">Stock</p>
                    <h6 class="text-sm">45021</h6>
                </div>
                <span class="material-icons stock-icon">
                    trending_up
                </span>
            </div>
            <div class="flex items-center justify-between w-1/4 rounded-lg px-4 box-border bg-[#FFFFFF] z-10">
                <div>
                    <p class="text-xs">Ticket</p>
                    <h6 class="text-sm">20516</h6>
                </div>
                <span class="material-icons ticket-icon">
                    confirmation_number
                </span>
            </div>
        </section>

    </section>
</template>


<script setup>

</script>
