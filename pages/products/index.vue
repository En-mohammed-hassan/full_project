<template lang="">
	<loading v-if="pending" />
	<div v-else>
		<ul>
			<li>
				<div class="grid lg:grid-cols-4 sm:grid-cols-2 gap-5">
					<div v-for="p in products">
						<productCard :product="p" />
					</div>
				</div>
			</li>
		</ul>
	</div>
</template>
<script setup>
	const { pending, data: products } = await useFetch(
		"https://fakestoreapi.com/products",
		{ lazy: true }
	);
</script>
<style lang=""></style>
