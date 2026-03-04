<script setup>
import { computed } from "vue";

const props = defineProps({
  reverse: {
    type: Boolean,
    default: false,
  },
  bgImage: {
    type: String,
    default: "",
  },
  logoSrc: {
    type: String,
    default: "",
  },
  logoAlt: {
    type: String,
    default: "",
  },
  sideSrc: {
    type: String,
    default: "",
  },
  sideAlt: {
    type: String,
    default: "",
  },
  title: {
    type: String,
    default: "",
  },
  paragraphs: {
    type: Array,
    default: () => [],
  },
});

const titleId = computed(
  () =>
    `section-${props.title.toLowerCase().replace(/\s+/g, "-").slice(0, 30)}`,
);
</script>

<template>
  <section
    :aria-labelledby="titleId"
    class="flex items-center bg-cover bg-center bg-no-repeat text-white p-8 lg:p-16 pb-8 lg:pb-32 relative"
    :style="{
      backgroundImage: `linear-gradient(
        to ${reverse ? 'bottom' : 'top'},
        rgba(0,0,0,0.70),
        rgba(0,0,0,0.4),
        rgba(0,0,0,0)
      ), url('${bgImage}')`,
    }"
  >
    <div
      class="flex flex-col max-lg:items-center gap-10 w-full"
      :class="reverse ? 'lg:flex-row-reverse' : 'lg:flex-row'"
    >
      <img :src="sideSrc" :alt="sideAlt" class="w-full lg:w-4xl object-cover" />

      <div
        class="flex flex-col gap-6 lg:gap-10 max-w-2xl max-lg:items-center max-lg:w-full"
      >
        <img
          v-if="logoSrc"
          :src="logoSrc"
          :alt="logoAlt"
          class="w-24 h-24 lg:w-40 lg:h-40"
        />

        <h2 :id="titleId" class="text-2xl lg:text-6xl max-lg:text-center">
          {{ title }}
        </h2>

        <p
          v-for="(para, i) in paragraphs"
          :key="i"
          class="text-sm lg:text-xl leading-relaxed font-chalet max-lg:text-center"
        >
          {{ para }}
        </p>
      </div>
    </div>
  </section>
</template>
