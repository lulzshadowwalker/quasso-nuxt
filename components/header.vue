<script setup lang="ts">
import { ref } from 'vue';

const visible = ref(false);
const search = ref('');

function show() {
  visible.value = true;
}

function blur() {
  visible.value = !!search.value.length;
}
</script>

<template>
  <header class="flex gap-6 justify-between max-w-screen-xl mx-auto px-2 py-4 items-center">
    <Logo />

    <!-- Search Bar -->
    <label class="input input-bordered flex items-center gap-2 max-w-xs w-min transition-all" @click="show">
      <input v-show="visible" type="text" class="grow" placeholder="Search" @blur="blur" v-model="search" />
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
        <path fill-rule="evenodd"
          d="M9.965 11.026a5 5 0 1 1 1.06-1.06l2.755 2.754a.75.75 0 1 1-1.06 1.06l-2.755-2.754ZM10.5 7a3.5 3.5 0 1 1-7 0 3.5 3.5 0 0 1 7 0Z"
          clip-rule="evenodd" />
      </svg>
    </label>
  </header>
</template>
