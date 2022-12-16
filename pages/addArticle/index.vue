<template>
  <header class="bg-[#173467] min-h-screen">
    <Nav />
    <p class="text-4xl pt-12 pl-24 underline text-white">
      Add new article
    </p>
    <div class="pl-24 pt-6">
      <div class="flex">
        <label class="pr-8 text-xl text-white block">Title</label>
        <input type="email" class="w-[25rem] h-8">
        <label class="pl-8 pr-[3.3rem] text-xl text-white block">Autor</label>
        <input type="email" class="w-[25rem] h-8">
      </div>
      <div class="flex pt-8">
        <label class="pr-4 text-xl text-white block">Image</label>
        <input type="email" class="w-[25rem] h-8">
        <label class="pl-8 pr-4 text-xl text-white block">Category</label>
        <input type="email" class="w-[25rem] h-8">
      </div>
      <div class="pt-8">
        <label class="pr-4 text-xl text-white block">Description</label>
        <textarea class="p-3 mt-5" name="comment" rows="7" cols="110" placeholder="Add Description.."></textarea>
      </div>
      <div class="pt-8">
        <input type="button" value="Submit" class="font-bold text-white bg-lime-500 rounded px-2 py-1 text-lg">
      </div>
    </div>
  </header>
  </template>