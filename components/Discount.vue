<template>
	<div class="flex flex-col items-center justify-center">
		<h1 class="text-center text-4xl uppercase font-semibold mb-16">
			Suggest your favorite topic
		</h1>
		<div class="text-center">
			<button @click='showModal = !showModal' class="block text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800" type="button">
				Suggest Topic
			</button>
				<div v-if='showModal == true' class="absolute left-[18rem] mt-4 block w-[25rem] h-[8rem]">
					<label class="text-xl text-white block">Topic</label>
					<div>
						<input type="text" class="w-[16rem] h-8 rounded text-black" placeholder="Enter a topic..." v-model='topic'>
						<button type="submit" class="bg-green-500 h-8 rounded ml-2 px-2">
							Send
						</button>
					</div>
				</div>
		</div>
	</div>
</template>

<script setup>
import { ref } from 'vue'
import { Dialog, DialogPanel, DialogTitle, TransitionChild, TransitionRoot } from '@headlessui/vue'

const open = ref(true)
const showModal = ref(false)
const topic = ref('')
</script>