<template>
  <div>
    <h2 class="section-title">Related Experiences</h2>

    <ul class="space-y-4">
      <li v-for="item in experienceList" :key="item.company">
        <div class="flex flex-1 justify-between">
          <div class="max-w-sm flex-1">
            <h3
              class="text-sm font-medium text-gray-900 group-hover:text-primary-600 dark:text-gray-100 dark:group-hover:text-primary-400">
              {{ item.company }}
            </h3>
            <p class="text-gray-500 dark:text-gray-300 text-xs my-1">
              {{ item.title }}
            </p>
            <p class="text-gray-500 dark:text-gray-300 text-sm my-1">
              {{ item.duration }}
            </p>
          </div>
        </div>
        <div class="flex flex-1 justify-between">
          <ul class="text-gray-600 dark:text-gray-400 text-sm list-disc list-inside">
            <li v-for="desc in item.description" :key="desc" class="text-justify">{{ desc }}</li>
          </ul>
        </div>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";

interface Experience {
  company: string;
  title: string;
  duration: string;
  description: string[];
}

const experienceList = ref<Experience[]>([
  // {
  //   company: "Hand Solutions Indonesia",
  //   title: "Monitoring Engineer",
  //   duration: "Aug 2024 - Present",
  //   description: [
  //     "Mainly responsible for the data analysis of background warnings for the customer team, and reporting problems in a timely manner.",
  //     "Monitor relevant systems, initially analyze relevant data, notify the business in a timely manner, and assist the business in making changes to customer needs.",
  //     "Comprehensively monitor the operation of existing systems, collect and organize data, and assist technology in secondary development of the system.",
  //   ],
  // },
  {
    company: "MZS Software House",
    title: "Software Engineer (Web)",
    duration: "Dec 2021 - Oct 2023",
    description: [
      "Experienced in creating, integrating, and managing databases, writing code using PHP (Laravel, CodeIgniter), developing web services such as Web and APIs, and integrating payment gateways. Also skilled in managing and developing Content Management Systems (CMS) and Hospital Management Systems (HMS). Implemented Test-Driven Development (TDD) and utilized CI/CD tools for automated testing and deployment.",
    ],
  },
]);
</script>

<style scoped>
ul {
  list-style-type: none;
}

.section-title {
  text-transform: uppercase;
  font-size: 0.75rem;
  /* text-xs */
  font-weight: 600;
  /* font-semibold */
  color: #9ca3af;
  /* text-gray-400 */
  margin-bottom: 1.5rem;
  /* mb-6 */
}
</style>
