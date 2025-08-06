<script setup lang="ts">
import Popover from "./components/Popover.vue";
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
</script>

<template>
  <section
    class="h-screen flex flex-col justify-center items-center bg-white text-center"
  >
    <h1 class="text-5xl font-bold mb-4">Welcome to PopLand</h1>
    <p class="text-lg text-gray-600 mb-6">
      A simple landing page to test popovers.
    </p>
    <button
      class="bg-blue-600 text-white px-6 py-2 rounded-full hover:bg-blue-700"
    >
      Only For Testing
    </button>
  </section>

  <!-- About -->
  <section id="about" class="py-20 px-4 bg-gray-50 text-center">
    <h2 class="text-3xl font-semibold mb-4">About This Page</h2>
    <p class="text-gray-700 max-w-xl mx-auto">
      This landing page is built using Vue and Tailwind CSS. It's designed to
      test a custom popover component located at the bottom right corner of the
      screen.
    </p>
  </section>
  <Popover :data="data" position="right" />
</template>
