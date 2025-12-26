<script setup>
import { ref } from 'vue';

// Data Skills dikategorikan agar lebih rapi
const skillCategories = ref([
    {
        name: "Frontend Development",
        items: [
            { name: "HTML5", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" },
            { name: "CSS3", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" },
            { name: "JavaScript", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" },
            { name: "Vue.js", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" },
            { name: "Tailwind CSS", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg" },
            // { name: "React", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" },
        ]
    },
    {
        name: "Backend Development",
        items: [
            { name: "PHP", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" },
            { name: "Python", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" },
            { name: "MySQL", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" },
            // { name: "SQLite", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sqlite/sqlite-original.svg" },
            { name: "Laravel", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/laravel/laravel-original.svg" },
            { name: "Django", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg" },
        ]
    },
    {
        name: "Tools & Others",
        items: [
            { name: "Git", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" },
            { name: "GitHub", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" },
            { name: "Figma", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg" },
            { name: "Notion", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/notion/notion-original.svg" },
            { name: "VS Code", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" },
            { name: "NPM", icon: "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/npm/npm-original-wordmark.svg" },
        ]
    }
]);
</script>

<template>
    <div class="relative mt-5 md:mt-20 p-6 md:p-10 w-full flex flex-col-reverse md:flex-row gap-2 bg-[#030E21]/60 rounded-3xl border-white/10 backdrop-blur-sm overflow-hidden">
        
        <div class="relative w-full md:w-1/3 xl:w-[25%] flex items-end justify-center md:justify-start">
             <img src="../assets/flat/Flat6.png" alt="Skills Illustration" class="w-60 md:w-full max-w-[300px] object-contain md:absolute md:bottom-[-20px] md:left-4 hover:scale-105 transition-transform duration-500">
        </div>

        <div class="w-full md:w-2/3 xl:w-full flex flex-col pl-0 md:pl-10 pb-10">
            <h2 class="text-4xl md:text-5xl font-bold text-white mb-6">My Skills</h2>
            
            <p class="text-[#868490] text-lg mb-8 leading-relaxed">
                Terus belajar dan berkembang adalah kunci. Berikut adalah teknologi dan *tools* yang saya gunakan sehari-hari untuk membangun website yang cepat dan responsif.
            </p>

            <div class="flex flex-col gap-8">
                <div v-for="(category, index) in skillCategories" :key="index">
                    <h3 class="text-amber-300 text-xl font-semibold mb-4 border-l-4 border-amber-300 pl-3">{{ category.name }}</h3>
                    
                    <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 gap-4">
                        <div 
                            v-for="skill in category.items" 
                            :key="skill.name"
                            class="group flex flex-col items-center justify-center p-4 rounded-xl bg-[#091427] border border-white/5 hover:border-amber-300/30 transition-all duration-300 hover:-translate-y-1 hover:shadow-lg hover:shadow-amber-500/10"
                        >
                            <img :src="skill.icon" :alt="skill.name" class="w-10 h-10 md:w-12 md:h-12 mb-2 group-hover:scale-110 transition-transform">
                            <span class="text-xs md:text-sm text-gray-400 group-hover:text-white font-medium">{{ skill.name }}</span>
                        </div>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<style scoped>
/* Tidak perlu CSS tambahan */
</style>