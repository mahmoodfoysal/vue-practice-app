<style scoped>
        .side-bar-bg {
        background-color: aliceblue;
        height: 562px;
    }
    .layout-sidebar {
        height: 562px;
        background-color: transparent;
    }

    .deviation-list {
    /* min-width: var(--sidebar-width); */
    width: 100%;
    border-right: 1px solid #e2edfa;
}

</style>
<template>
    <section class="layout-sidebar deviation-list">
        <div class="ps-5 pt-5">
        <ul>
            <li>Fruits & Vegetables
                <ul class="ms-5">
                    <li>Fresh Vegetables</li>
                    <li>Fresh Fruits</li>
                </ul>
            </li>
            <li>Meat & Fish
                <ul class="ms-5">
                    <li>Chicken & Poultry</li>
                    <li>Premium Perishables</li>
                    <li>Frozen Fish</li>
                    <li>Meat</li>
                    <li>Dried Fish</li>
                </ul>
            </li>
            <li>Cooking
                <ul class="ms-5">
                    <li>Spices</li>
                    <li>Salt & Sugar</li>
                    <li>Rice</li>
                    <li>Dal or Lentil</li>
                    <li>Ready Mix</li>
                    <li>Oil</li>
                    <li>Ghee</li>
                </ul>
            </li>
        </ul>
    </div>
    </section>
</template>

<script setup>

</script>