<script setup>
import TaskBlock from './components/TaskBlock.vue'

import {ref, onMounted, watch} from 'vue'

const tasks = ref([])
const input_value = ref('')

</script>

<template>
  <main class="w-full h-svh grid grid-cols-1 grid-rows-[1fr_auto] bg-slate-200">
    <section class="overflow-auto rounded-b-3xl grid grid-cols-1 grid-rows-[auto_1fr]">
      <h1 class="text-3xl text-center py-2">
        To Do: {{ input_value.value }}
      </h1>
      <div class="overflow-auto bg-white rounded-2xl px-2 py-3 space-y-2">
        <TaskBlock v-for="i in 25" :key="i" />
      </div>
    </section>
    <section class="px-6 py-4 w-full flex items-center justify-between space-x-2">
      <input type="text" placeholder="E.g. Make VUE app"
      class="w-full h-full px-2 rounded-md" v-model="input_value">
      <button class="bg-slate-600 hover:bg-slate-700 transition-all p-2 px-4 h-full rounded-md text-white flex justify-center items-center">+</button>
    </section>
  </main>
</template>