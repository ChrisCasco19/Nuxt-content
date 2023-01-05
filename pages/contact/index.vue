<template>
  <header class="bg-[#173467] min-h-screen">
    <Nav />
    <p class="text-xl pt-8 px-10 text-white">
      Contact us, let us know your concerns, your thoughts, comments, questions, suggestions and all your points of view. It will be a pleasure for us to share time with you.
    </p>
    <div class="pt-16">
      <div class="flex justify-center">
        <label class="pr-4 text-3xl text-white">Email Address</label>
        <input type="email" class="w-[12rem]" v-model="email" placeholder="Enter your email">
        <label class="px-4 text-3xl text-white">First Name</label>
        <input type="text" class="w-[12rem]" v-model="firstName" placeholder="Enter your first Name">
      </div>
      <div class="flex justify-center pt-8">
        <label class="text-3xl mx-8 text-white">Last Name</label>
        <input type="text" class="w-[12rem] mr-2" v-model="lastName" placeholder="Enter your Last name">
        <label class="text-3xl ml-8 mr-8 text-white">Country</label>
        <input type="text" class="w-[12rem]" v-model="country" placeholder="Enter your Country">
      </div>
      <div class="flex justify-center pt-8">
        <label for="number" class="mx-8 text-3xl text-white">Cell phone</label>
        <input type="number" class="w-[12rem]" v-model="cellPhoneNumber" placeholder="Enter your Cell Phone number">
        <label for="email" class="pl-4 pr-4 text-3xl text-white">Code Zone</label>
        <input type="text" class="w-[12rem]" v-model="codeZone" placeholder="Enter your Code zone">
      </div>
      <div class="flex justify-center text-white font bold text-3xl pt-8">
        <label for="">Comment</label>
      </div>
      <div class="flex justify-center pt-4">
        <textarea class="p-3" name="comment" rows="3" cols="60" placeholder="Add Comment.."></textarea>
      </div>
      <div class="flex justify-center pt-8">
        <input type="button" value="Submit" class="font-bold text-white bg-lime-500 rounded px-2 py-1 text-lg">
      </div>
    </div>
  </header>
</template>
<script setup>
import { ref } from 'vue'

const email = ref('')
const firstName = ref('')
const lastName = ref('')
const country = ref('')
const cellPhoneNumber = ref()
const codeZone = ref()

</script>