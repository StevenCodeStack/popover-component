<script lang="ts" setup>
import { ref } from "vue";
import LogoPrimakara from "/icons/logo only.svg";

// Props
const data = [
  {
    id: 1,
    title: "Sistem Absensi",
    icon: "/icons/icon-sistem-absensi.svg",
    link: "/",
  },
  { id: 2, title: "Elearn", icon: "/icons/icon-elearn.svg", link: "/" },
  {
    id: 3,
    title: "Sistem Akademik",
    icon: "/icons/icon-sistem-akademik.svg",
    link: "/index",
  },
  {
    id: 4,
    title: "Sistem Kepegawaian",
    icon: "/icons/icon-sistem-kepegawaian.svg",
    link: "/",
  },
  { id: 5, title: "SSO", icon: "/icons/icon-sso.svg", link: "/" },
  {
    id: 1,
    title: "Sistem Absensi",
    icon: "/icons/icon-sistem-absensi.svg",
    link: "/",
  },
  { id: 2, title: "Elearn", icon: "/icons/icon-elearn.svg", link: "/" },
  {
    id: 3,
    title: "Sistem Akademik",
    icon: "/icons/icon-sistem-akademik.svg",
    link: "/",
  },
  {
    id: 4,
    title: "Sistem Kepegawaian",
    icon: "/icons/icon-sistem-kepegawaian.svg",
    link: "/",
  },
  { id: 5, title: "SSO", icon: "/icons/icon-sso.svg", link: "/" },
];
let isOpen = ref(false);
</script>

<template>
  <div :class="['fixed bottom-8 inline-block z-100', 'right-8']">
    <!-- Popover -->
    <div
      :class="[
        'absolute bottom-full mb-2 bg-white border border-slate-300 z-10 rounded-2xl transition-all ease-in-out',
        isOpen
          ? 'w-90 h-100 opacity-100 p-3 py-6 border shadow-lg'
          : 'w-0 h-0 -z-1 p-0',
        '-translate-x-[90%] left-0',
      ]"
    >
      <div
        class="grid grid-cols-3 gap-3 gap-y-0 overflow-scroll hideScrollBar h-full overflow-x-hidden"
      >
        <div v-for="item in data" :key="item.id">
          <!-- Items -->
          <a
            :href="item.link"
            class="flex flex-col gap-1 items-center hover:bg-[#f1f1f1] rounded-2xl justify-center p-3 transition-all cursor-pointer"
          >
            <img :src="item.icon" class="h-20 w-20" />
            <p class="text-center text-xs text-black font-semibold">
              {{ item.title }}
            </p>
          </a>
        </div>
      </div>
    </div>

    <!-- Trigger Button -->
    <div
      @click="isOpen = !isOpen"
      class="bg-white shadow-2xl gradientbutton border border-slate-300 w-16 h-16 flex justify-center items-center rounded-full z-100 cursor-pointer hover:bg-[#edf8ff]"
    >
      <img :src="LogoPrimakara" class="w-8 h-8" />
    </div>
  </div>
</template>

<style>
.gradientbutton:hover {
  background: linear-gradient(to top, #ccc, white);
}
</style>
