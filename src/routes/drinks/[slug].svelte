<script context="module">
	export function preload({ params, query }) {
		return {ingredientName: params.slug}
	}
</script>

<script>
	import { onMount } from 'svelte';
	import  DrinkCard  from '../../components/DrinkCard.svelte';

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

	.drink-list {
		margin-top: 30px;
	}
</style>

<div class="main">
    <h1 class="is-size-3">{ingredientName}</h1>
	<div class="drink-list">
		<div class="columns is-multiline">
				{#each drinks as drink}
						<DrinkCard
							name="{drink.strDrink}"
							imageUrl="{drink.strDrinkThumb}"
						/>
				{/each}
		</div>
	</div>
</div>