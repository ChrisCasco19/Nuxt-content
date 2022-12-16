<template>
	<header class="flex items-center justify-between h-20 px-[5%] lg:px-[15%] bg-[#173467]">
		<NuxtLink to="/" class="text-2xl font-bold lg:text-4xl">
			<img src="https://res.cloudinary.com/guidedsteps/image/upload/v1648756929/white_guidedsteps_v4_color_mark_text_copy.svg" class="w-[300px]"/>
		</NuxtLink>
		<nav class="flex items-center text-gray-600 space-x-7">
			<template v-for="(n, i) in links" :key="`navLink-${i}`">
				<NuxtLink
					:to="n.link"
					class="inline-block text-white nav-link hover:text-primary group"
				>
					<div class="flex items-center space-x-2">
						<Icon :icon="n.icon" class="w-4 h-4 text-white" />
						<span class="font-medium text-white"> {{ n.name }}</span>
					</div>
					<div
						class="h-0.5 w-4/5 bg-primary mt-1 -translate-y-full scale-0 group-hover:scale-100 group-hover:translate-y-full transition-all"
					></div>
				</NuxtLink>
			</template>
		</nav>
	</header>
</template>

<script setup>
	import { Icon } from "@iconify/vue";
	const links = [
		{
			name: "Home",
			icon: "material-symbols:home",
			link: "/",
		},
		{
			name: "Articles",
			icon: "mdi:blog-outline",
			link: "/articles",
		},
		{
			name: "Add Articles",
			icon: "material-symbols:add-box-outline",
			link: "/addArticle",
		},
		{
			name: "About",
			icon: "mdi:about-circle-outline",
			link: "/about",
		},
		{
			name: "Contact",
			icon: "material-symbols:connect-without-contact",
			link: "/contact",
		},
	];
</script>

<style scoped>
	.nav-link.router-link-active.router-link-exact-active {
		@apply text-primary;
	}
</style>