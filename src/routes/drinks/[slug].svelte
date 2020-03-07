<script context="module">
	export function preload({ params, query }) {
		return {ingredientName: params.slug}
	}
</script>

<script>
	import { onMount } from 'svelte';

	export let ingredientName;
	let drinks = [];

	onMount(() => {
		fetch(`https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=${ingredientName}`)
		.then(res => {
			if(!res.ok) {
				throw new Error('Failed Fetching Drinks');
			}

			return  res.json();
		})
		.then(data => {
			drinks = data.drinks;
		})
		
	})
</script>

<style>
    .main {
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 80vh;
	}
</style>

<div class="main">
    <h1 class="is-size-3">{ingredientName}</h1>
	<ul>
		{#each drinks as drink}
			 <li>{drink.strDrink}</li>
		{/each}
	</ul>
</div>