<template>
  <header class="bg-[#173467] min-h-screen">
    <Nav />
    <p class="text-4xl pt-12 pl-24 underline text-white">
      Add new article
    </p>
    <div class="pl-24 pt-6">
      <div class="flex">
        <label class="pr-8 text-xl text-white block">Title</label>
        <input type="text" class="w-[25rem] h-8" v-model='title'>
        <label class="pl-8 pr-[3.3rem] text-xl text-white block">Author</label>
        <input type="text" class="w-[25rem] h-8" v-model='author'>
      </div>
      <div class="flex pt-8">
        <label class="pr-4 text-xl text-white block">Image</label>
        <input type="file" accept="image/png, image/jpeg" class="w-[25rem] h-8 text-white">
        <label class="pl-8 pr-4 text-xl text-white block">Category</label>
        <input type="text" v-model='category' class="w-[25rem] h-8">
      </div>
      <div class="pt-8">
        <label class="pr-4 text-xl text-white block">Description</label>
        <textarea class="p-3 mt-5" v-model='description' name="comment" rows="7" cols="110" placeholder="Add Description.."></textarea>
      </div>
      <div class="pt-8">
        <input type="button" value="Submit" class="font-bold text-white bg-lime-500 rounded px-2 py-1 text-lg cursor-pointer">
      </div>
    </div>
  </header>
</template>
<script setup>
import { ref } from 'vue'

const title = ref('')
const description = ref('')
const category = ref('')
const author = ref('')
</script>