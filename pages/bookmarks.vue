<script setup>
useSeoMeta({
  title: "Bookmarks | Agus Syahril Mubarok",
  description,
});

const description =
  "Explore my curated collection of bookmarks, where I save the most inspiring, insightful, and resourceful content I've discovered.";

const bookmarks = [
  {
    id: 3,
    label: "開篇詞 時光之鏡：透視過去、現在與未來的 Observability",
    url: "https://ithelp.ithome.com.tw/articles/10319053",
  },
  {
    id: 2,
    label: "DevOps Roadmap for 2024",
    url: "https://github.com/milanm/DevOps-Roadmap",
  },
  {
    id: 1,
    label: "Zooper a beautiful and minimal portfolio site made with Nuxt 3",
    url: "https://github.com/fayazara/zooper",
  },
];

function getHost(url) {
  const parsedUrl = new URL(url);
  let host = parsedUrl.host;
  if (host.startsWith("www.")) {
    host = host.substring(4);
  }
  return host;
}

function getThumbnail(url) {
  const host = getHost(url);
  return `https://logo.clearbit.com/${host}`;
}
</script>

<template>
  <main class="min-h-screen">
    <AppHeader class="mb-8" title="Bookmarks" :description="description" />
    <ul class="space-y-2">
      <li v-for="bookmark in bookmarks" :key="bookmark.id">
        <a
          :href="bookmark.url"
          target="_blank"
          class="flex items-center gap-3 hover:bg-gray-100 dark:hover:bg-white/10 p-2 rounded-lg -m-2 text-sm min-w-0"
        >
          <UAvatar
            :src="getThumbnail(bookmark.url)"
            :alt="bookmark.label"
            :ui="{ rounded: 'rounded-md' }"
          />
          <p class="truncate text-gray-700 dark:text-gray-200">
            {{ bookmark.label }}
          </p>
          <span class="flex-1"></span>
          <span class="text-xs font-medium text-gray-400 dark:text-gray-600">
            {{ getHost(bookmark.url) }}
          </span>
        </a>
      </li>
    </ul>
  </main>
</template>
