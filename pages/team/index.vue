<template>
  <header class="bg-[#173467] min-h-screen">
    <Nav />
    <div class="flex justify-center">
      <template v-for="(n, i) in users" :key="i">
        <div class="max-w-sm rounded overflow-hidden shadow-lg bg-slate-500 m-2 w-[24rem]">
          <div class="flex justify-center m-2">
            <img src="https://cdn-icons-png.flaticon.com/512/149/149071.png" class="w-36" alt="">
          </div>
          <div class="px-6 py-4">
            <div class="font-bold text-3xl mb-2">{{ n.name }}</div>
            <p class="text-white text-base">
              {{ n.description }}
            </p>
          </div>
          <div class="px-6 pt-4 pb-2">
            <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#Development</span>
            <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2">#Design</span>      </div>
        </div>
      </template>
    </div>
  </header>
</template>

<script setup>
	const users = [
		{
			name: "Jeremy R. DeYoung",
			icon: "material-symbols:home",
			link: "/",
      description: 'Senior developer'
		},
		{
			name: "Dixy Barahona",
			icon: "mdi:blog-outline",
			link: "/articles",
      description: 'Senior developer'
		},
		{
			name: "Christian Casco",
			icon: "material-symbols:add-box-outline",
			link: "/addArticle",
      description: 'Junior developer'
		},
	];
</script>