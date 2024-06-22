<script lang="ts" setup>
const backgrounds = [
  "from-violet-300 to-indigo-300 dark:from-violet-600 dark:to-indigo-600",
  "from-sky-300 to-blue-300 dark:from-sky-600 dark:to-blue-600",
  "from-teal-300 to-cyan-300 dark:from-teal-600 dark:to-cyan-600",
];

let index = 0;
function randomBackground() {
  const background = backgrounds[index];

  index = index < backgrounds.length - 1 ? index + 1 : 0;

  return background;
}

const projects = [
  {
    name: "Ember Breadcrumbs",
    description: "Template-based breadcrumb management for Ember applications.",
    tags: ["Ember", "TypeScript"],
    url: "https://github.com/Bagaar/ember-breadcrumbs",
  },
  {
    name: "Ember Flat to Nested",
    description:
      "Transform a flat colocated to a nested colocated component structure.",
    tags: ["JavaScript", "Node"],
    url: "https://github.com/bertdeblock/ember-flat-to-nested",
  },
  {
    name: "Ember GraphQL Mocking",
    description: "Mock GraphQL requests using Mock Service Worker.",
    tags: ["Ember", "GraphQL", "TypeScript"],
    url: "https://github.com/Bagaar/ember-graphql-mocking",
  },
  {
    name: "Ember Intl Commands",
    description: "Useful commands for managing ember-intl translation files.",
    tags: ["JavaScript", "Node"],
    url: "https://github.com/bertdeblock/ember-intl-commands",
  },
  {
    name: "Ember Pagination",
    description:
      "Easy customisable pagination component for Ember applications.",
    tags: ["Ember", "TypeScript"],
    url: "https://github.com/Bagaar/ember-pagination",
  },
  {
    name: "Ember Permissions",
    description: "Permission management for Ember applications.",
    tags: ["Ember", "TypeScript"],
    url: "https://github.com/Bagaar/ember-permissions",
  },
  {
    name: "Gember",
    description:
      "Generate components, helpers, modifiers and services in v2 addons.",
    tags: ["Node", "TypeScript"],
    url: "https://github.com/bertdeblock/gember",
  },
  {
    name: "Generate Template Registry",
    description: "Generate a template registry for Glint.",
    tags: ["Node", "TypeScript"],
    url: "https://github.com/bertdeblock/generate-template-registry",
  },
  {
    name: "Try or Die",
    description:
      "An experiment inspired by ember-try, but decoupled from ember-cli.",
    tags: ["Node", "TypeScript"],
    url: "https://github.com/bertdeblock/try-or-die",
  },
  {
    name: "Velvet Thunder",
    description:
      "A semi-headless UI library built for Ember using Tailwind CSS.",
    tags: ["Ember", "Tailwind", "TypeScript"],
    url: "https://velvet-thunder.netlify.app/",
  },
];

const socials = [
  {
    name: "Facebook",
    url: "https://facebook.com/borrtt",
    icon: `
      <svg
        class="size-4"
        fill="currentColor"
        viewBox="0 0 512 512"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
            d="M512 256C512 114.6 397.4 0 256 0S0 114.6 0 256C0 376 82.7 476.8 194.2 504.5V334.2H141.4V256h52.8V222.3c0-87.1 39.4-127.5 125-127.5c16.2 0 44.2 3.2 55.7 6.4V172c-6-.6-16.5-1-29.6-1c-42 0-58.2 15.9-58.2 57.2V256h83.6l-14.4 78.2H287V510.1C413.8 494.8 512 386.9 512 256h0z"
        />
      </svg>
    `,
  },
  {
    name: "GitHub",
    url: "https://github.com/bertdeblock",
    icon: `
      <svg
        class="size-4"
        fill="currentColor"
        viewBox="0 0 496 512"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
            d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3 .3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5 .3-6.2 2.3zm44.2-1.7c-2.9 .7-4.9 2.6-4.6 4.9 .3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3 .7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3 .3 2.9 2.3 3.9 1.6 1 3.6 .7 4.3-.7 .7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3 .7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3 .7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"
        />
      </svg>
    `,
  },
  {
    name: "Instagram",
    url: "https://instagram.com/borrtt",
    icon: `
      <svg
        class="size-4"
        fill="currentColor"
        viewBox="0 0 448 512"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
            d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
        />
      </svg>
    `,
  },
  {
    name: "LinkedIn",
    url: "https://linkedin.com/in/bert-de-block",
    icon: `
      <svg
        class="size-4"
        fill="currentColor"
        viewBox="0 0 448 512"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
            d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"
        />
      </svg>
    `,
  },
  {
    name: "Strava",
    url: "https://strava.com/athletes/11926148",
    icon: `
      <svg
        class="size-4"
        fill="currentColor"
        viewBox="0 0 384 512"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
            d="M158.4 0L7 292h89.2l62.2-116.1L220.1 292h88.5zm150.2 292l-43.9 88.2-44.6-88.2h-67.6l112.2 220 111.5-220z"
        />
      </svg>
    `,
  },
];

const yearsOfExperience = new Date().getFullYear() - 2012;
</script>

<template>
  <div class="space-y-8 md:flex md:items-center md:space-x-8 md:space-y-0">
    <img
      alt="Bert De Block"
      class="size-56 shrink-0 rounded-xl border border-slate-200 dark:border-slate-700"
      src="public/bert.jpeg"
    />

    <div>
      <h2 class="heading-xl mb-8">Hi, I'm Bert!</h2>
      <p>
        I’m a passionate
        <span class="highlight">Senior Front-end Developer</span>
        with {{ yearsOfExperience }}+ years of experience in building Web
        Applications. I'm also an
        <a class="highlight" href="https://emberjs.com/teams/" target="_blank">
          Ember CLI Core Team Emeritus</a
        >. <br /><br />
        I enjoy building beautiful online experiences, always with the end user
        in mind.
        <br /><br />
        Over the years, I've also become more and more interested in developing
        and improving tooling to help make teams more productive.
      </p>
    </div>
  </div>

  <div>
    <h2 class="heading-xl mb-8">Open-Source Projects</h2>

    <div class="grid grid-cols-1 gap-8 md:grid-cols-2">
      <div
        v-for="project in projects"
        :class="randomBackground()"
        class="relative flex min-h-56 flex-col rounded-xl bg-gradient-to-r p-8 transition-transform duration-[400ms] hover:-translate-y-2"
      >
        <h3 class="heading-lg mb-2">
          <a
            :href="project.url"
            class="after:absolute after:inset-0"
            target="_blank"
          >
            {{ project.name }}
          </a>
        </h3>

        <p class="grow">
          {{ project.description }}
        </p>

        <ul class="flex items-center space-x-2">
          <li v-for="tag in project.tags" class="tag">
            {{ tag }}
          </li>
        </ul>
      </div>
    </div>
  </div>

  <div>
    <h2 class="heading-xl mb-8">Find Me On</h2>

    <ul class="space-y-2">
      <li v-for="social in socials">
        <a
          :href="social.url"
          class="link flex w-fit items-center space-x-2"
          target="_blank"
        >
          <span v-html="social.icon"></span>
          <span>
            {{ social.name }}
          </span>
        </a>
      </li>
    </ul>
  </div>

  <div>
    <p class="text-xs">&copy; 2024 • Bert De Block</p>
  </div>
</template>
