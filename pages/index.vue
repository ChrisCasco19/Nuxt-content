<template>
	<div class="min-h-screen min-w-screen bg-[#173467]">
		<Nav />
		<main>
			<section class="lg:px-[15%] px-[5%] pt-20">
				<h1
					class="text-3xl font-semibold leading-normal text-center text-white lg:text-5xl"
				>
				" A Blog About "
				</h1>
				<h1
					class="text-4xl font-bold leading-normal text-center lg:text-6xl rainbow-text"
				>
					Faith, confidence and Love
				</h1>
			</section>
			<section class="lg:px-[15%] px-[5%] lg:pt-20 pt-14">
				<p
					class="mb-10 font-medium tracking-wider text-center text-gray-500 uppercase"
				>
					About the prayers
				</p>
				<div class="grid grid-cols-1 gap-5 lg:grid-cols-3">
					<template
						v-for="(b, i) in blogNav[0].children"
						:key="`blogNavItem-${b._path}-${i}`"
					>
						<div class="py-5 border-2 rounded-lg px-7">
							<div class="flex justify-between">
								<h2 class="text-lg font-bold underline text-white">
									{{ b.title }}
								</h2>
								<img src="https://res.cloudinary.com/guidedsteps/image/upload/v1648827271/guidedsteps_color_mark_white.svg" class="w-10">
							</div>
							<!-- Loop over files inside the content dir -->
							<ul
								v-if="b.children"
								class="pl-2 mt-4 space-y-3 list-disc list-inside"
							>
								<template
									v-for="(child, k) in b.children"
									:key="`childNav-${child._path}-${k}-${i}`"
								>
									<li
										class="text-sm text-white transition-all list-item hover:text-yellow-500"
									>
										<NuxtLink :to="`/blog${child._path}`">
											{{ child.title }}
										</NuxtLink>
									</li>
								</template>
							</ul>
							<ul v-else class="pl-2 mt-4 space-y-3 list-disc list-inside">
								<li
									class="text-sm text-white transition-all list-item hover:text-yellow-500"
								>
									<NuxtLink :to="`/blog${b._path}`"> Show More </NuxtLink>
								</li>
							</ul>
						</div>
					</template>
				</div>
			</section>
		</main>
	</div>
</template>

<script setup>
	const { data: blogNav } = await useAsyncData("navigation", () => {
		return fetchContentNavigation(queryContent("blog"));
	});
	useHead({
		title: "Content Blog",
	});
</script>