<template>
	<!-- detail -->
	<section class="body-font overflow-hidden">
		<div class="container px-5 py-24 mx-auto">
			<div class="lg:w-4/5 mx-auto flex flex-wrap">
				<img
					alt="ecommerce"
					class="lg:w-1/2 w-full object-cover object-center rounded border border-gray-200"
					:src="mangaById.attributes.posterImage.original"
				/>
				<div class="lg:w-1/2 w-full lg:pl-10 lg:py-6 mt-6 lg:mt-0">
					<router-link
						class="text-sm title-font text-yellow-500 tracking-widest"
						to="/"
					>
						back Home
					</router-link>
					<h1 class="text-white text-3xl title-font font-medium mb-1">
						{{ mangaById.attributes.titles.en_jp }}
					</h1>
					<div class="flex mb-4">
						<span class="flex ml-3 pl-3 py-2 border-l-2 border-gray-200">
							<a class="text-gray-500">
								<svg
									fill="currentColor"
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									class="w-5 h-5"
									viewBox="0 0 24 24"
								>
									<path
										d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"
									></path>
								</svg>
							</a>
							<a class="ml-2 text-gray-500">
								<svg
									fill="currentColor"
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									class="w-5 h-5"
									viewBox="0 0 24 24"
								>
									<path
										d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"
									></path>
								</svg>
							</a>
							<a class="ml-2 text-gray-500">
								<svg
									fill="currentColor"
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									class="w-5 h-5"
									viewBox="0 0 24 24"
								>
									<path
										d="M21 11.5a8.38 8.38 0 01-.9 3.8 8.5 8.5 0 01-7.6 4.7 8.38 8.38 0 01-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 01-.9-3.8 8.5 8.5 0 014.7-7.6 8.38 8.38 0 013.8-.9h.5a8.48 8.48 0 018 8v.5z"
									></path>
								</svg>
							</a>
						</span>
					</div>
					<p class="leading-relaxed text-white">
						{{ mangaById.attributes.description }}
					</p>
					<div class="flex">
						<span class="title-font font-medium text-2xl text-red-500">
							{{ mangaById.attributes.averageRating }}
						</span>
						<router-link
							class="flex ml-auto text-white bg-sky-500 border-0 py-2 px-6 focus:outline-none hover:bg-red-600 rounded-2xl"
							to="/"
						>
							Back
						</router-link>
					</div>
				</div>
			</div>
		</div>
	</section>
	<!-- end of detail -->
</template>

<script>
	export default {
		name: "DetailPage",
		methods: {
			getMangaById() {
				this.$store.dispatch("getMangaById", this.$route.params.id);
			},
		},
		computed: {
			mangaById() {
				return this.$store.state.mangaById;
			},
		},
		created() {
			this.getMangaById();
		},
	};
</script>

<style></style>
