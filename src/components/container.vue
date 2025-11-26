<script setup>
    import AboutMe from './aboutMe.vue';
    import Header from './header.vue';
    import Portofolio from './portofolio.vue';
    import Skills from './skills.vue';
    import Footer from './footer.vue';
    import Hero from './hero.vue';
    
    // Logika Spotlight Mouse
    import { ref, onMounted, onUnmounted } from 'vue';

    const mouseX = ref(0);
    const mouseY = ref(0);

    function handleMouseMove(event) {
        mouseX.value = event.clientX;
        mouseY.value = event.clientY;
    }

    onMounted(() => {
        window.addEventListener('mousemove', handleMouseMove);
    });

    onUnmounted(() => {
        window.removeEventListener('mousemove', handleMouseMove);
    });
</script>

<template>
    <div class="relative isolate w-full min-h-screen">
        
        <div 
            class="pointer-events-none fixed inset-0 z-30 transition-opacity duration-300"
            :style="{
                background: `radial-gradient(600px circle at ${mouseX}px ${mouseY}px, rgba(94, 107, 255, 0.10), transparent 40%)`
            }"
        ></div>

        <img src="../assets/glow/v1.png" alt="" class="absolute z-[-1]">
        <img src="../assets/glow/v2.svg" alt="" class="absolute z-[-1] right-0 top-48 md:top-100">
        <img src="../assets/glow/v3.svg" alt="" class="absolute z-[-1] left-0 top-48 md:top-300">
        <img src="../assets/glow/v4.svg" alt="" class="absolute z-[-1] right-0 top-48 md:top-700">
        
        <Header></Header>
        <div class="w-full h-full pt-7 px-7 md:px-12 xl:px-28">    
            <Hero id="home"></Hero>
            <AboutMe id="about"></AboutMe>
            <Portofolio id="portofolio"></Portofolio>
            <Skills id="skills"></Skills>
        </div>
        
        <Footer id="contact"></Footer>
    </div>
</template>

<style scoped>
</style>