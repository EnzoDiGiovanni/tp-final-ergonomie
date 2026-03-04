<script setup>
import { ref } from "vue";

const menuOpen = ref(false);
const toggle = () => {
  menuOpen.value = !menuOpen.value;
};
const close = () => {
  menuOpen.value = false;
};

const navLinks = [
  { label: "VUE D'ENSEMBLE", href: "#overview" },
  { label: "GTA ONLINE", href: "#online", hasDropdown: true },
  { label: "HISTOIRE", href: "#history", hasDropdown: true },
  { label: "PLUS", href: "#more", hasDropdown: true },
];
</script>

<template>
  <a
    href="#main-content"
    class="sr-only focus:not-sr-only focus:fixed focus:top-2 focus:left-2 focus:z-400 focus:bg-white focus:text-black focus:px-4 focus:py-2 focus:rounded focus:font-bold focus:text-sm"
  >
    Aller au contenu principal
  </a>

  <header
    role="banner"
    class="sticky top-0 z-100 px-4 py-2 lg:p-10 bg-rs-dark border-b border-neutral-800"
  >
    <div class="flex items-center justify-between">
      <div class="flex items-center gap-3">
        <button
          type="button"
          aria-label="Mon compte"
          class="lg:hidden focus-rs p-2 text-white"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="18"
            height="18"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
            aria-hidden="true"
          >
            <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" />
            <circle cx="12" cy="7" r="4" />
          </svg>
        </button>

        <a
          href="/"
          aria-label="Rockstar Games — GTA V, retour à l'accueil"
          class="focus-rs flex items-center gap-3 shrink-0"
          @click="close"
        >
          <img
            src="./images/r-logo.svg"
            alt="Rockstar Games"
            width="240"
            height="56"
            class="h-10 w-auto hidden sm:block border-r-2 border-r-white"
          />
          <img
            src="./images/logo.svg"
            alt="Grand Theft Auto V"
            width="240"
            height="56"
            class="h-10 w-auto hidden sm:block"
          />
        </a>
      </div>

      <nav
        aria-label="Navigation principale"
        class="hidden lg:flex items-center gap-12"
      >
        <a
          v-for="link in navLinks"
          :key="link.label"
          :href="link.href"
          class="nav-link-rs px-5"
          :aria-haspopup="link.hasDropdown ? 'true' : undefined"
        >
          {{ link.label }}
          <svg
            v-if="link.hasDropdown"
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2.5"
            aria-hidden="true"
          >
            <polyline points="6 9 12 15 18 9" />
          </svg>
        </a>
      </nav>

      <div class="flex items-center gap-3">
        <div class="hidden lg:flex items-center gap-3">
          <a href="#buy" class="btn-rs-outline"> Acheter maintenant </a>

          <button
            type="button"
            aria-label="Rechercher"
            class="focus-rs p-2 text-white hover:bg-neutral-400/30 cursor-pointer rounded-full transition-colors"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="size-6"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"
              />
            </svg>
          </button>

          <button
            type="button"
            aria-label="Mon compte Rockstar"
            class="focus-rs p-2 text-white hover:bg-neutral-400/30 cursor-pointer rounded-full transition-colors"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="size-6"
              aria-hidden="true"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M15.75 6a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0ZM4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.933 17.933 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632Z"
              />
            </svg>
          </button>
        </div>

        <button
          type="button"
          :aria-expanded="menuOpen.toString()"
          aria-controls="mobile-drawer"
          :aria-label="menuOpen ? 'Fermer le menu' : 'Ouvrir le menu'"
          class="lg:hidden focus-rs p-2 text-white"
          @click="toggle"
        >
          <span class="flex flex-col gap-1.25 w-5" aria-hidden="true">
            <span
              class="block h-0.5 bg-white rounded transition-all duration-300 origin-center"
              :class="menuOpen ? 'rotate-45 translate-y-1.75' : ''"
            ></span>
            <span
              class="block h-0.5 bg-white rounded transition-all duration-300"
              :class="menuOpen ? 'opacity-0 scale-x-0' : ''"
            ></span>
            <span
              class="block h-0.5 bg-white rounded transition-all duration-300 origin-center"
              :class="menuOpen ? '-rotate-45 -translate-y-1.75' : ''"
            ></span>
          </span>
        </button>
      </div>
    </div>

    <nav
      id="mobile-drawer"
      role="navigation"
      aria-label="Menu mobile"
      :aria-hidden="(!menuOpen).toString()"
      class="lg:hidden overflow-hidden transition-all duration-300"
      :class="
        menuOpen
          ? 'max-h-screen opacity-100'
          : 'max-h-0 opacity-0 pointer-events-none'
      "
    >
      <div class="bg-rs-dark px-5 pt-4 pb-6">
        <div
          class="flex items-center gap-2 bg-rs-surface rounded px-3 py-2.5 mb-4"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16"
            height="16"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
            aria-hidden="true"
            class="text-neutral-400 shrink-0"
          >
            <circle cx="11" cy="11" r="8" />
            <path d="m21 21-4.35-4.35" />
          </svg>
          <label for="mobile-search" class="sr-only"
            >Rechercher sur Rockstar Games</label
          >
          <input
            id="mobile-search"
            type="search"
            placeholder="Rechercher sur Rockstar Games"
            class="bg-transparent text-white text-sm w-full outline-none placeholder:text-neutral-400"
          />
        </div>

        <ul role="list" class="flex flex-col">
          <li v-for="link in navLinks" :key="link.label">
            <a :href="link.href" class="nav-link-mobile" @click="close">
              {{ link.label }}
              <svg
                v-if="link.hasDropdown"
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                aria-hidden="true"
              >
                <polyline points="6 9 12 15 18 9" />
              </svg>
            </a>
          </li>
          <li>
            <a href="#assistance" class="nav-link-mobile" @click="close">
              Assistance
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="14"
                height="14"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="2"
                aria-hidden="true"
              >
                <path
                  d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"
                />
                <polyline points="15 3 21 3 21 9" />
                <line x1="10" x2="21" y1="14" y2="3" />
              </svg>
            </a>
          </li>
        </ul>

        <a
          href="#buy"
          class="btn-rs-outline w-full mt-5 text-center py-5"
          @click="close"
        >
          Acheter maintenant
        </a>
      </div>
    </nav>
  </header>
</template>
