<template>
  <ul class="grid sm:grid-cols-2 grid-cols-1 gap-8 col-span-3 md:col-span-8">
    <div v-for="blog in data?.contents" :key="blog.id" class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
      <NuxtLink :to="`/${blog.id}`">
        <a href="#">
            <img :src="blog.eyecatch?.url" class="rounded-t-lg" alt="" />
        </a>
        <div class="p-5">
            <a href="#">
                <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ blog.title }}</h5>
            </a>
            <div class="inline-block rounded border-2 border-teal-600 px-1.5 py-0.5 text-sm font-semibold text-teal-600">{{ blog.category?.name }}</div>
            <div class="mt-1 text-sm text-gray-700">{{ dateFormat(blog.publishedAt ?? blog.createdAt) }}</div>
            <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">{{ blog.explain }}</p>
            <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-teal-700 rounded-lg hover:bg-teal-800 focus:ring-4 focus:outline-none focus:ring-teal-300 dark:bg-teal-600 dark:hover:bg-teal-700 dark:focus:ring-teal-800">
                Read more
                <svg class="w-3.5 h-3.5 ml-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                </svg>
            </a>
        </div>
      </NuxtLink>
    </div>
  </ul>
</template>

<script setup lang="ts">
import { Blog } from "~~/types/Blog";

const { data } = await useMicroCMSGetList<Blog>({
  endpoint: "blogs",
});
console.log(data);
</script>