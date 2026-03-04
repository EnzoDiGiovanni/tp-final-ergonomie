<script setup>
import { computed } from "vue";

const props = defineProps({
  imageSrc: { type: String, required: true },
  imageAlt: { type: String, default: "" },
  title: { type: String, required: true },
  text: { type: String, required: true },
  reverse: { type: Boolean, default: false },
});

const titleId = computed(
  () =>
    `feature-${props.title.toLowerCase().replace(/\s+/g, "-").slice(0, 30)}`,
);
</script>

<template>
  <section
    :aria-labelledby="titleId"
    class="flex flex-col bg-rs-surface max-lg:items-center px-6 py-10 lg:px-16 lg:py-20 lg:items-center lg:justify-around text-white"
    :class="reverse ? 'lg:flex-row-reverse' : 'lg:flex-row'"
  >
    <img
      :src="imageSrc"
      :alt="imageAlt"
      class="w-full lg:w-1/2 max-lg:w-[90%] shrink-0 rounded-lg object-cover"
    />

    <div class="max-w-lg flex flex-col gap-6 lg:gap-10 mt-6 lg:mt-0">
      <h2 :id="titleId" class="text-2xl lg:text-6xl font-bold">
        {{ title }}
      </h2>
      <p class="text-sm lg:text-base leading-7 lg:leading-8 text-gray-300">
        {{ text }}
      </p>
    </div>
  </section>
</template>
