<script lang="ts" setup>
useHead({
  title: "Bert De Block",
  link: [{ rel: "icon", type: "image/png", href: "/favicon.svg" }],
  script: [
    {
      innerHTML: `
        const html = document.querySelector("html");
        const favicon = document.querySelector("[rel='icon']");
        const prefersDarkMode = window.matchMedia("(prefers-color-scheme: dark)").matches;

        if (localStorage.mode === "dark" || (!localStorage.mode && prefersDarkMode)) {
          html.classList.add("dark");
        } else {
          html.classList.remove("dark");
        }

        if (prefersDarkMode) {
          favicon.href = "/favicon-dark.svg";
        } else {
          favicon.href = "/favicon.svg";
        }
      `,
    },
  ],
});

useSeoMeta({
  title: "Bert De Block",
  ogTitle: "Bert De Block",
  description: "Senior Front-end Developer • Ember CLI Core Team Emeritus",
  ogDescription: "Senior Front-end Developer • Ember CLI Core Team Emeritus",
  ogImage: "/public/bert.jpeg",
});

const toggleDarkMode = () => {
  const html = document.querySelector("html");

  if (html.classList.contains("dark")) {
    html.classList.remove("dark");
    localStorage.setItem("mode", "light");
  } else {
    html.classList.add("dark");
    localStorage.setItem("mode", "dark");
  }
};
</script>

<template>
  <header
    class="sticky left-0 top-0 z-10 w-full border-b border-slate-200 bg-white/90 backdrop-blur dark:border-slate-700 dark:bg-slate-800/90"
  >
    <div class="container flex items-center justify-between py-8">
      <h1 class="heading-xl">
        <NuxtLink to="/">Bert De Block</NuxtLink>
      </h1>

      <ul class="flex items-center space-x-4">
        <!-- <li>
          <NuxtLink
            aria-label="Music I Like"
            class="link block"
            title="Music I Like"
            to="/music"
          >
            <svg
              class="size-4"
              fill="currentColor"
              viewBox="0 0 512 512"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M499.1 6.3c8.1 6 12.9 15.6 12.9 25.7v72V368c0 44.2-43 80-96 80s-96-35.8-96-80s43-80 96-80c11.2 0 22 1.6 32 4.6V147L192 223.8V432c0 44.2-43 80-96 80s-96-35.8-96-80s43-80 96-80c11.2 0 22 1.6 32 4.6V200 128c0-14.1 9.3-26.6 22.8-30.7l320-96c9.7-2.9 20.2-1.1 28.3 5z"
              />
            </svg>
          </NuxtLink>
        </li> -->

        <li>
          <button
            @click="toggleDarkMode()"
            aria-label="Toggle Dark Mode"
            class="link block"
            title="Toggle Dark Mode"
            type="button"
          >
            <svg
              class="size-4"
              fill="currentColor"
              viewBox="0 0 512 512"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M448 256c0-106-86-192-192-192V448c106 0 192-86 192-192zM0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256z"
              />
            </svg>
          </button>
        </li>
      </ul>
    </div>
  </header>

  <div class="container space-y-16 pb-8 pt-16 md:space-y-32 md:pb-16 md:pt-32">
    <NuxtPage />
  </div>
</template>
