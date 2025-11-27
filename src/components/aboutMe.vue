<script setup>
import { ref } from 'vue';

// Data Biografi
const bio = ref({
    description: `Saya adalah seorang Frontend Developer dengan semangat tinggi untuk membangun solusi digital yang fungsional dan menarik secara visual. Saya memiliki pengalaman dalam mengubah desain UI/UX menjadi kode yang bersih dan efisien.`,
    subDescription: `Saya nyaman bekerja dengan berbagai teknologi modern dan selalu antusias untuk mempelajari hal-hal baru di dunia pengembangan web. Saat ini saya sedang fokus mendalami ekosistem Vue.js.`
});

// Data Highlights (Kartu Info di sebelah kanan)
const highlights = ref([
    {
        id: 1,
        title: "Pendidikan",
        subtitle: "S1 - Teknik Informatika",
        note: "Universitas Nusantara PGRI Kediri (2021 - 2025)", // Ganti sesuai datamu
        icon: "🎓" 
    },
    {
        id: 2,
        title: "Pengalaman",
        subtitle: "Freelance & Project",
        note: "1+ Tahun Pengalaman",
        icon: "💼"
    },
    {
        id: 3,
        title: "Status",
        subtitle: "Open for Projects",
        note: "Remote / On-site",
        icon: "🚀"
    }
]);
</script>

<template>
    <div class="relative mt-5 md:mt-20 p-6 md:p-10 md:py-25 w-full flex flex-col md:flex-row gap-6 bg-[#030E21]/60 rounded-3xl border-white/10 backdrop-blur-sm overflow-hidden">
        
        <img src="../assets/flat/Flat8.png" alt="Profile Character" class="absolute -bottom-4 -left-10 xl:left-10 w-48 md:w-64 xl:w-80 opacity-20 md:opacity-100 pointer-events-none z-0">

        <div class="hidden md:block md:w-1/3 xl:w-[25%]"></div>

        <div class="w-full flex flex-col z-10 pl-0 md:pl-6">
            <h2 class="text-4xl md:text-5xl font-bold text-white mb-6">About Me</h2>
            
            <div class="flex flex-col xl:flex-row gap-8">
                <div class="w-full xl:w-3/5 text-[#868490] text-lg leading-relaxed flex flex-col gap-4 text-justify md:text-left">
                    <p>{{ bio.description }}</p>
                    <p>{{ bio.subDescription }}</p>
                    
                    <!-- <div class="mt-4 flex flex-wrap gap-4">
                        <a href="#" class="px-6 py-3 bg-amber-300 hover:bg-amber-400 text-black font-bold rounded-xl transition-colors shadow-[0_0_15px_rgba(252,211,77,0.3)]">
                            Download CV
                        </a>
                        <a href="#" class="px-6 py-3 border border-white/20 hover:bg-white/5 text-white font-medium rounded-xl transition-colors">
                            Contact Me
                        </a>
                    </div> -->
                </div>

                <div class="w-full xl:w-2/5 flex flex-col gap-4">
                    <div v-for="item in highlights" :key="item.id" class="group flex flex-row items-center gap-4 p-4 rounded-2xl bg-[#091427] border border-white/5 hover:border-amber-300/30 transition-all duration-300 hover:-translate-y-1">
                        <div class="w-12 h-12 rounded-full bg-white/5 group-hover:bg-amber-300/10 flex items-center justify-center text-2xl transition-colors">
                            {{ item.icon }}
                        </div>
                        <div>
                            <h3 class="font-bold text-white text-lg group-hover:text-amber-100">{{ item.title }}</h3>
                            <p class="text-amber-300 text-sm font-medium">{{ item.subtitle }}</p>
                            <p class="text-gray-500 text-xs mt-0.5">{{ item.note }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
/* Opsional: Tambahan styling jika diperlukan */
</style>