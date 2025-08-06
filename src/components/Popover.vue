<script lang="ts" setup>
import { ref } from "vue";

type Position = "left" | "right";

const { data, position } = withDefaults(
  defineProps<{
    data: { id: number; title: string; icon: string; link: string }[];
    position?: Position;
  }>(),
  {
    position: "right",
  }
);

let positionClass =
  position == "right"
    ? "-translate-x-[90%] left-0"
    : "translate-x-[90%] right-0";
let isOpen = ref(true);
</script>

<template>
  <div
    :class="[
      'fixed bottom-5 inline-block z-100',
      position === 'right' ? 'right-5' : 'left-5',
    ]"
  >
    <!-- Popover -->
    <div
      :class="[
        'absolute bottom-full mb-2 bg-[#171717] z-10 rounded-2xl transition-all ease-in-out',
        isOpen
          ? 'w-90 h-100 opacity-100 p-3 py-6 border shadow-lg'
          : 'w-0 h-0 -z-1 p-0',
        positionClass,
      ]"
    >
      <div
        class="grid grid-cols-3 gap-3 gap-y-0 overflow-scroll hideScrollBar h-full"
      >
        <div v-for="item in data" :key="item.id">
          <a :href="item.link" class="flex flex-col gap-1 items-center">
            <img :src="item.icon" class="h-16 w-16" />
            <p class="text-center shrink-0 text-xs text-white font-semibold">
              {{ item.title }}
            </p>
            ></a
          >
        </div>
      </div>
    </div>

    <!-- Trigger Button -->
    <button
      @click="isOpen = !isOpen"
      class="p-6 bg-black rounded-full z-100"
    ></button>
  </div>
</template>

<style>
.hideScrollBar {
  scrollbar-width: none;
}
</style>
