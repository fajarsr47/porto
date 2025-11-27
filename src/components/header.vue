<script setup>
// import logoImg from '@/assets/logo/logoPutih.png';
</script>

<template>
    <div class="sticky top-0 z-50 w-full h-16 md:h-20 mx-auto flex flex-row justify-between items-center backdrop-blur-md rounded-b-2xl px-7 md:px-12 xl:px-28 transition-all">
        
        <a href="#home">
            <img src="../assets/logo/logoPutih.png" alt="LOGO" class="h-8 md:h-10 cursor-pointer hover:opacity-80 transition-opacity">
        </a>
        
        <div class="hidden md:flex flex-row gap-8">
            <a href="#home" class="text-[#9E9CA6] font-medium hover:text-white hover:scale-105 transition-all">Home</a>
            <a href="#about" class="text-[#9E9CA6] font-medium hover:text-white hover:scale-105 transition-all">About</a>
            <a href="#portofolio" class="text-[#9E9CA6] font-medium hover:text-white hover:scale-105 transition-all">Portofolio</a>
            <a href="#skills" class="text-[#9E9CA6] font-medium hover:text-white hover:scale-105 transition-all">Skills</a>
        </div>

        <a href="#contact" class="px-5 py-2 rounded-full border border-white/20 text-white text-sm font-medium hover:bg-white/10 transition-colors">
            Contact Me
        </a>
    </div>
</template>

<style scoped>
</style>