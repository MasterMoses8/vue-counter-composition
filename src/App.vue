<!-- 
  composition api.
  declare use of composition api but calling setup in script tag.
  be aware of the syntax required.
-->
<script setup>
	// import ref from vue library which will be used to declare reactive state
	import { ref } from 'vue';

	// invoke ref on count constant to identify it as reactive
	const count = ref(0);

	// create arrow function to increase count
	const addToCount = () => {
		// when called increase value of count state variable by 1
		count.value++;
	};

	// create arrow function to decrease count
	const subtractFromCount = () => {
		// when called decrease value of count state variable by 1
		count.value--;
	};
</script>

<!-- javascript template to render the html for the page -->
<template>
	<main>
		<div>
			<h4>The current count is...</h4>
			<!-- access value of count state object -->
			<h1>{{ count }}</h1>
			<!-- button calls on click listener to use subtrack function -->
			<button @click="subtractFromCount">-</button>
			<!-- button calls on click listener to use add function -->
			<button @click="addToCount">+</button>
		</div>
	</main>
</template>

<!-- scoped style will affect only this component -->
<style scoped>
	main {
		height: 100vh;
		width: 100vw;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	div {
		text-align: center;
	}
</style>
