<script context="module">
	export function preload({ params, query }) {
		return {drinkName: params.slug}
	}
</script>

<script>
    export let drinkName;
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
    <h1 class="is-size-3">{drinkName}</h1>
</div>