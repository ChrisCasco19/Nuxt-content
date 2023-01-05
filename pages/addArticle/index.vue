<template>
  <header class="bg-[#173467] min-h-screen">
    <Nav />
    <p class="text-4xl pt-12 pl-24 underline text-white">
      Add new article
    </p>
    <div class="pl-24 pt-6">
      <div class="flex">
        <label class="pr-8 text-xl text-white block">Title</label>
        <input type="text" class="w-[25rem] h-8" placeholder="Enter a title" v-model='addTitle'>
        <label class="pl-8 pr-[3.3rem] text-xl text-white block">Price</label>
        <input type="number" class="w-[25rem] h-8" placeholder="Enter a Price" v-model='addPrice'>
      </div>
      <div class="flex pt-8">
        <label class="pr-4 text-xl text-white block">Image</label>
        <input type="file" accept="image/png, image/jpeg" class="w-[25rem] h-8 text-white">
        <label class="pl-8 pr-4 text-xl text-white block">Category</label>
        <input type="text" v-model='addCategory' class="w-[25rem] h-8" placeholder="Enter a Category">
      </div>
      <div class="pt-8">
        <label class="pr-4 text-xl text-white block">Description</label>
        <textarea class="p-3 mt-5" v-model='addDescription' name="comment" rows="7" cols="110" placeholder="Add Description.."></textarea>
      </div>
      <div class="pt-8">
        <button type="submit" @click="addProduct" class="font-bold text-white bg-lime-500 rounded px-2 py-1 text-lg cursor-pointer">
          Save article
        </button>
      </div>
    </div>
  </header>
</template>
<script setup>
import { ref } from 'vue'

const addTitle = ref('')
const addDescription = ref('')
const addCategory = ref('')
const addPrice = ref('')
const image = ref()

async function addProduct(){ await fetch('https://fakestoreapi.com/products',{
            method:"POST",
            body:JSON.stringify(
                {
                  title: addTitle,
                  price: addPrice,
                  description: addDescription,
                  image: 'https://i.pravatar.cc',
                    category: addCategory
                }
            )
        })
            .then(res=>res.json())
            .then(json=>console.log(json))
            console.log('add', addProduct)
      }

</script>