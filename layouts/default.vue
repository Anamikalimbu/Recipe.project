<template>
    <div>
        <header>
            <Navbar />
        </header>
        <main>
            <slot></slot>
        </main>
        <footer>
            <Last />
        </footer>
    </div>
</template>

<script setup>
import { onMounted } from 'vue'
import { initFlowbite } from 'flowbite'

// initialize components based on data attribute selectors
onMounted(() => {
    initFlowbite();
})
</script>

<style scoped>

</style>