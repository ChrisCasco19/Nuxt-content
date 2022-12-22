<template>
	<div>
		<Nav />
		<main>
			<section class="lg:px-[10%] pt-10 px-[5%]">
				<div class="flex relative items-start flex-col lg:flex-row gap-7">
					<div class="flex-1">
						<img
							class="w-full object-contain h-[90%]"
							:src="data[id - 1].image"
							:alt="data[id - 1].title"
						/>
					</div>
					<div class="flex-1">
						<p
							class="capitalize text-sm px-4 py-1 bg-gray-200 inline-block rounded text-gray-500"
						>
							
						</p>
						<h1 class="font-bold lg:text-3xl text-2xl my-5 lg:my-6">
							{{ data[id - 1].title }}
						</h1>
						<div class="flex items-center space-x-1">
							<template v-for="(r, i) in 5" :key="`productRating-${i}`">
								<Icon
									icon="ri:star-fill"
									:class="{
										'text-primary-500': i < parseInt(data[id -1].rating.rate),
										'text-gray-300': i >= parseInt(data[id -1].rating.rate),
									}"
								/>
							</template>
							<span class="text-xs ml-2"
								>{{ data[id - 1].rating.count }} reviews</span
							>
						</div>

						<p class="lg:text-3xl text-2xl mt-8">
							{{ data[id -1 ].price }} $
						</p>
						<p
							class="mt-5 text-gray-500 whitespace-pre-wrap text-sm lg:text-base"
							v-html="data[id - 1].description"
						></p>
						<div class="mt-12 flex items-center space-x-5">
							<button class="rainbow-bg text-white py-4 rounded-md w-full">
								Like
							</button>
							<button>
								<Icon icon="ph:heart-straight" class="text-gray-500 hover:text-red-700 w-7 h-7" />
							</button>
						</div>
					</div>
				</div>
			</section>
			<br />
		</main>
	</div>
</template>

<script setup>
	import { Icon } from "@iconify/vue";
	const id = useRoute().params.id;


	const data = await fetch('https://fakestoreapi.com/products/')
  .then(res=>res.json())
  .then((json) => json)
	console.log('data', data)

	// function used to format the price
	const formatPrice = (price) => {
		return new Intl.NumberFormat("en-US", {
			style: "currency",
			currency: "USD",
		}).format(price);
	};

	// Set header
</script>

<style></style>