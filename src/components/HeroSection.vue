<script setup></script>

<template>
  <section
    class="flex items-center bg-cover bg-center bg-no-repeat text-white p-6 lg:p-16 relative min-h-screen"
    style="
      background-image: linear-gradient(
          to right,
          rgba(0, 0, 0, 0.85),
          rgba(0, 0, 0, 0.4),
          rgba(0, 0, 0, 0)
        ),
        url(&quot;/herobg.jpeg&quot;);
    "
  >
    <img
      src="./icons/tilt.svg"
      alt=""
      aria-hidden="true"
      class="w-full h-14 absolute top-0 left-0 Z-1"
    />
    <img
      src="./icons/tiltgray.svg"
      alt=""
      aria-hidden="true"
      class="w-full h-14 absolute bottom-0 left-0 scale-y-[-1] z-1"
    />
    <div class="flex flex-col gap-8 lg:gap-20 z-10 max-lg:items-center max-lg:w-full">
      <div class="flex items-center gap-4 lg:gap-6">
        <img
          src="./images/gtaV.svg"
          alt="Logo GTA V"
          class="w-20 h-20 lg:w-40 lg:h-40"
        />
        <img
          src="./images/gtaonline.svg"
          alt="Logo GTA Online"
          class="w-20 h-20 lg:w-38 lg:h-38"
        />
      </div>
      <div class="flex flex-col gap-3 lg:gap-6">
        <h1
          class="text-xl lg:text-5xl max-lg:text-center font-chalet font-bold"
        >
          Maintenant pour PlayStation 5,<br />
          Xbox Series X|S et PC
        </h1>
        <p class="text-sm lg:text-2xl max-lg:text-center">
          Découvrez Grand Theft Auto V et GTA Online, les <br />
          deux blockbusters incontournables.
        </p>
      </div>
      <div class="flex flex-col lg:flex-row items-center lg:items-start gap-3 lg:gap-4">
        <button
          type="button"
          class="px-6 py-2 lg:px-20 lg:py-6 rounded-sm border-2 border-white text-xs lg:text-2xl hover:bg-white hover:text-black ease-in transition-all cursor-pointer"
        >
          REGARDER LA BANDE ANNNONCE
        </button>
        <button
          type="button"
          class="px-6 py-2 lg:px-20 lg:py-6 rounded-sm border-2 border-white text-xs lg:text-2xl hover:bg-white hover:text-black ease-in transition-all cursor-pointer"
        >
          ACHETER MAINTENANT
        </button>
      </div>
    </div>
  </section>
</template>
