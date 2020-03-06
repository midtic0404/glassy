<script>
	let ingredients = ['Vodka', 'Tequila', 'Rum', 'Jin', 'Tripple Sec']
</script>

<style>
	.main {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 80vh;
	}

	.columns {
		margin-top: 50px;
	}
</style>

<div class="main">
	<h1 class="is-size-3">Select An Ingredient</h1>
	<div class="columns is-multiline is-centered">
		{#each ingredients as ingredient, index (index)}
			<!-- <NoteCard 
			description="{note}"
			on:delete={deleteNote(index)} /> -->
			<div class="column">
				<a href='drinks/{ingredient}' class="button is-medium is-link is-light">{ ingredient} </a>
			</div>
		{/each}
	</div>
</div>



