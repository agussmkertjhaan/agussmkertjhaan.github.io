<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div>
    <h1
      class="text-2xl font-bold tracking-tight text-zinc-800 dark:text-zinc-100"
    >
      {{ title }} /on
      <a
        href="https://medium.com/@agussyahrilmubarok"
        class="hover:underline hover:text-cyan-500"
        target="_blank"
        rel="noopener noreferrer"
        >Medium</a
      >
    </h1>
    <p class="mt-6 text-base text-gray-600 dark:text-gray-400">
      {{ description }}
    </p>
  </div>
</template>
