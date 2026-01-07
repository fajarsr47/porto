<script setup>
import { ref, computed } from "vue";
import presensi from '../assets/foto/presensi.png'
import skin from '../assets/foto/skin.png'

const projects = ref([
  {
    id: 1,
    title: "Presensi Face Recognition",
    category: "Fullstack",
    image: presensi,
    desc: "Website presensi sekolah menggunakan pengenalan wajah dengan fitur spesial real-time pelaporan kepada wali siswa melalui WhatsApp",
    github: "https://fajarsr47.github.io/FacePresensi/",
  },
  {
    id: 1,
    title: "Rekomendasi Bahan Aktif Skincare",
    category: "Frontend",
    image:
      skin,
    desc: "Website untuk merekomendasikan bahan aktif skincare menggunakan foto wajah untuk mendeteksi jenis kulit dan penyakit pada kulit wajah",
    github: "https://fajarsr47.github.io/rhiscare/",
  },
  {
    id: 3,
    title: "Dashboard Gudang",
    category: "Frontend",
    image:
      "https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=1000&auto=format&fit=crop",
    desc: "Desain antarmuka dashboard admin untuk memantau analitik data penjualan. Mengambil public API dari dummyjson.com",
    github: "https://gudang.setiawan.biz.id",
  },
  // {
  //     id: 4,
  //     title: "Mobile App Design",
  //     category: "Mobile Design",
  //     image: "https://images.unsplash.com/photo-1512941937669-90a1b58e7e9c?q=80&w=1000&auto=format&fit=crop",
  //     desc: "Konsep desain aplikasi mobile untuk travel booking dengan fokus pada pengalaman pengguna (UX).",
  //     github: "https://github.com/fajar-sr47/travel-app-design"
  // },
  // {
  //     id: 5,
  //     title: "Sistem Manajemen",
  //     category: "Fullstack",
  //     image: "https://images.unsplash.com/photo-1517694712202-14dd9538aa97?q=80&w=1000&auto=format&fit=crop",
  //     desc: "Aplikasi berbasis web untuk manajemen inventaris barang masuk dan keluar di gudang.",
  //     github: "https://github.com/fajar-sr47/inventory-system"
  // },
  // {
  //     id: 6,
  //     title: "Personal Blog",
  //     category: "Web Development",
  //     image: "https://images.unsplash.com/photo-1499750310159-525446b095ef?q=80&w=1000&auto=format&fit=crop",
  //     desc: "Blog pribadi menggunakan Markdown untuk konten, dibangun dengan Vue.js dan Tailwind CSS.",
  //     github: "https://github.com/fajar-sr47/my-blog"
  // },
  // {
  //     id: 7,
  //     title: "Weather App",
  //     category: "API Integration",
  //     image: "https://images.unsplash.com/photo-1592210454359-9043f067919b?q=80&w=1000&auto=format&fit=crop",
  //     desc: "Aplikasi cuaca sederhana yang mengambil data real-time dari OpenWeatherMap API.",
  //     github: "https://github.com/fajar-sr47/weather-app"
  // },
  // {
  //     id: 8,
  //     title: "Movie Database",
  //     category: "Frontend",
  //     image: "https://images.unsplash.com/photo-1489599849927-2ee91cede3ba?q=80&w=1000&auto=format&fit=crop",
  //     desc: "Katalog film yang memungkinkan pengguna mencari film favorit dan melihat rating serta sinopsis.",
  //     github: "https://github.com/fajar-sr47/movie-db"
  // },
  // {
  //     id: 9,
  //     title: "Chat Application",
  //     category: "Realtime App",
  //     image: "https://images.unsplash.com/photo-1611162617474-5b21e879e113?q=80&w=1000&auto=format&fit=crop",
  //     desc: "Aplikasi chatting real-time menggunakan WebSocket dan Firebase.",
  //     github: "https://github.com/fajar-sr47/chat-app"
  // }
]);

// --- 2. LOGIKA TOGGLE ---
const initialLimit = 6;
const limit = ref(initialLimit);
const isExpanded = computed(() => limit.value > initialLimit);
const displayedProjects = computed(() => {
  return projects.value.slice(0, limit.value);
});
function toggleProjects() {
  if (isExpanded.value) {
    limit.value = initialLimit;
  } else {
    limit.value = projects.value.length;
  }
}

// --- 3. LOGIKA POPUP ---
const selectedProject = ref(null);
function openModal(project) {
  selectedProject.value = project;
  document.body.style.overflow = "hidden";
}
function closeModal() {
  selectedProject.value = null;
  document.body.style.overflow = "auto";
}
</script>

<template>
  <div
    id="portofolio"
    class="relative mt-5 md:mt-20 p-6 md:p-10 w-full flex flex-col md:flex-row gap-2 border-white/10 bg-[#030E21]/60 rounded-3xl backdrop-blur-sm overflow-hidden md:overflow-visible"
  >
    <img
      src="../assets/flat/Flat4B.png"
      alt="Decoration"
      class="absolute -bottom-4 -right-10 md:right-10 w-60 md:w-80 opacity-50 md:opacity-100 pointer-events-none z-[-1] md:z-0"
    />

    <div class="h-full w-full flex flex-col z-10">
      <div class="flex flex-row justify-between items-end mb-8">
        <div>
          <h2 class="text-4xl md:text-5xl font-bold text-white mb-2">
            My Portofolio
          </h2>
          <p class="text-gray-400">
            Beberapa project pilihan yang telah saya kerjakan
          </p>
        </div>

        <button
          v-if="projects.length > initialLimit"
          @click="toggleProjects"
          class="hidden md:block text-lg font-medium transition-colors cursor-pointer"
          :class="
            isExpanded
              ? 'text-red-400 hover:text-red-300'
              : 'text-amber-300 hover:text-amber-400'
          "
        >
          {{ isExpanded ? "Show Less <-" : "See More ->" }}
        </button>
      </div>

      <div
        class="w-full grid grid-cols-1 md:grid-cols-2 xl:grid-cols-3 gap-6 pr-0 md:pr-40 xl:pr-80"
      >
        <div
          v-for="project in displayedProjects"
          :key="project.id"
          @click="openModal(project)"
          class="group relative h-30 md:42 lg:h-64 w-full rounded-2xl shadow-xl overflow-hidden cursor-pointer border border-white/5 hover:border-amber-300/50 transition-all duration-300 hover:-translate-y-2 bg-[#091427]"
        >
          <img
            :src="project.image"
            :alt="project.title"
            class="absolute inset-0 w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          />
          <div
            class="absolute inset-0 bg-linear-to-t from-black/90 via-black/40 to-transparent opacity-80 group-hover:opacity-90 transition-opacity"
          ></div>

          <div
            class="absolute bottom-0 left-0 p-5 w-full transform translate-y-2 group-hover:translate-y-0 transition-transform duration-300"
          >
            <span
              class="text-amber-300 text-xs font-semibold tracking-wider uppercase"
              >{{ project.category }}</span
            >
            <h3
              class="text-lg lg:text-xl font-bold text-white mt-1 group-hover:text-amber-100"
            >
              {{ project.title }}
            </h3>
            <p
              class="text-xs text-gray-300 mt-2 opacity-0 group-hover:opacity-100 transition-opacity"
            >
              Klik untuk detail
            </p>
          </div>
        </div>

        <div
          v-if="projects.length > initialLimit"
          class="md:hidden h-20 w-full rounded-2xl border border-dashed flex items-center justify-center cursor-pointer transition-colors"
          :class="
            isExpanded
              ? 'border-red-400/30 hover:bg-red-900/10'
              : 'border-white/20 hover:bg-white/5'
          "
          @click="toggleProjects"
        >
          <span
            class="font-medium"
            :class="isExpanded ? 'text-red-400' : 'text-amber-300'"
          >
            {{ isExpanded ? "Show Less Projects <-" : "Load More Projects ->" }}
          </span>
        </div>
      </div>
    </div>
  </div>

  <div
    v-if="selectedProject"
    class="fixed inset-0 z-50 flex items-center justify-center p-4"
  >
    <div
      class="absolute inset-0 bg-black/80 backdrop-blur-sm"
      @click="closeModal"
    ></div>
    <div
      class="relative bg-[#091427] border border-white/10 w-full max-w-2xl rounded-2xl overflow-hidden shadow-2xl flex flex-col md:flex-row animate-fadeIn"
    >
      <button
        @click="closeModal"
        class="absolute top-4 right-4 z-20 bg-black/50 hover:bg-red-500 text-white w-8 h-8 rounded-full flex items-center justify-center transition-colors"
      >
        &times;
      </button>
      <div class="w-full md:w-1/2 h-48 md:h-auto relative">
        <img
          :src="selectedProject.image"
          class="w-full h-full object-cover"
          alt="Project Image"
        />
      </div>
      <div class="w-full md:w-1/2 p-6 md:p-8 flex flex-col justify-center">
        <span
          class="text-amber-300 text-sm font-bold uppercase tracking-wide mb-2"
          >{{ selectedProject.category }}</span
        >
        <h3 class="text-3xl font-bold text-white mb-4">
          {{ selectedProject.title }}
        </h3>
        <p class="text-gray-300 mb-8 leading-relaxed">
          {{ selectedProject.desc }}
        </p>
        <a
          :href="selectedProject.github"
          target="_blank"
          class="w-fit flex items-center gap-2 bg-white text-black hover:bg-amber-300 px-5 py-2.5 rounded-lg font-bold transition-all transform hover:scale-105"
        >
          <!-- <img
            src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg"
            class="w-5 h-5"
            alt="GitHub"
          /> -->
          Kunjungi
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
.animate-fadeIn {
  animation: fadeIn 0.2s ease-out forwards;
}
</style>
