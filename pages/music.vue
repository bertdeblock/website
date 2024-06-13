<script lang="ts" setup>
import { computed, ref } from "vue";

useHead({ title: "Music • Bert De Block" });

type Tags = string[];
type Entry = {
  src: string;
  tags: Tags;
};

const entries: Entry[] = [
  {
    src: "https://open.spotify.com/embed/track/7A9hbRAiHFC74aZLjZYIio",
    tags: ["Track"],
  },
  {
    src: "https://open.spotify.com/embed/album/4wXzmsXCXVn3REyPK2Z4M3",
    tags: ["Album"],
  },
  {
    src: "https://open.spotify.com/embed/album/4wXzmsXCXVn3REyPK2Z4M3",
    tags: ["Album"],
  },
  {
    src: "https://open.spotify.com/embed/track/7A9hbRAiHFC74aZLjZYIio",
    tags: ["Track"],
  },
];

const tags: Tags = new Set(entries.map((entry) => entry.tags).flat());
const activeTags = ref([...tags]);

const entriesForActiveTags = computed(() => {
  return entries.filter((entry) => {
    return entry.tags.some((tag) => activeTags.value.includes(tag));
  });
});

function isTagActive(tag: string): boolean {
  return activeTags.value.includes(tag);
}

function toggleTag(tag: string): void {
  if (isTagActive(tag)) {
    activeTags.value.splice(activeTags.value.indexOf(tag), 1);
  } else {
    activeTags.value.push(tag);
  }
}
</script>

<template>
  <div class="space-y-8">
    <ul class="flex items-center space-x-2">
      <li v-for="tag in tags">
        <button
          @click="toggleTag(tag)"
          :class="
            isTagActive(tag)
              ? 'bg-slate-900/20 dark:bg-white/40'
              : 'bg-slate-900/10 dark:bg-white/20'
          "
          class="tag"
        >
          {{ tag }}
        </button>
      </li>
    </ul>

    <div class="grid grid-cols-1 gap-8 md:grid-cols-2">
      <iframe
        v-for="entry in entriesForActiveTags"
        :src="entry.src"
        allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture;"
        allowfullscreen
        class="rounded-3xl"
        frameBorder="0"
        height="152"
        loading="lazy"
        width="100%"
      ></iframe>
    </div>
  </div>
</template>
