<script setup>
  import jobData from '@/jobs.json';
  import { ref } from 'vue';

  // Define a reactive reference to store job listings
  const jobs = ref(jobData.jobs); // Access the 'jobs' array from jobData

  console.log(jobs.value); // Output to verify data

</script>

<template>
    <div v-for="job in jobs" :key="job.id">
          <div class="bg-white rounded-xl shadow-md relative">
            <div class="p-4">
              <div class="mb-6">
                <div class="text-gray-600 my-2">{{ job.type }}</div>
                <h3 class="text-xl font-bold">{{ job.title}}</h3>
              </div>

              <div class="mb-5">
               {{ job.description}}
              </div>

              <h3 class="text-green-500 mb-2">{{ job.salary}}</h3>

              <div class="border border-gray-100 mb-5"></div>

              <div class="flex flex-col lg:flex-row justify-between mb-4">
                <div class="text-orange-700 mb-3">
                  <i class="fa-solid fa-location-dot text-lg"></i>
                {{ job.locatioin}}
                </div>
                <a
                  href="job.html"
                  class="h-[36px] bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg text-center text-sm"
                >
                  Read More
                </a>
              </div>
            </div>
          </div>
      </div>
  </template>

<style scoped>
  /* Add scoped styles here */
</style>