<script setup>
    import AboutMe from './aboutMe.vue';
    import Header from './header.vue';
    import Portofolio from './portofolio.vue';
    import Skills from './skills.vue';
    import Footer from './footer.vue';
    import Hero from './hero.vue';
</script>

<template>
    <div class="relative isolate w-full">
        <img src="../assets/glow/v1.png" alt="" class="absolute -z-1">
        <img src="../assets/glow/v2.svg" alt="" class="absolute -z-1 right-0 top-48 md:top-100">
        <img src="../assets/glow/v3.svg" alt="" class="absolute -z-1 left-0 top-48 md:top-300">
        <img src="../assets/glow/v4.svg" alt="" class="absolute -z-1 right-0 top-48 md:top-700">

        <div class="w-full h-full pt-7 px-7 md:px-12 xl:px-28">
            <Header></Header>
            <Hero></Hero>
            <AboutMe></AboutMe>
            <Portofolio></Portofolio>
            <Skills></Skills>
        </div>
        <Footer></Footer>
    </div>
</template>

<style scoped>

</style>