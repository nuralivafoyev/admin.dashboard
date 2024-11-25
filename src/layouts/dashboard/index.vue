<template>
    <Header />

    <main>
        <Navigation />
        <section id="routing">
            <!-- routing -->
        </section>
    </main>
    
    <Footer />
</template>

<script setup>
import Navigation from '../../components/navigation/index.vue';
import Header from '../../components/header/index.vue';
import Footer from "../../components/footer/index.vue"
</script>

<style scoped lang="scss" src="./_style.scss"></style>