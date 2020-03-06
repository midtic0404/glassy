<script>
	import Header from '../components/Header.svelte';

	export let segment;
</script>

<style>
	main {
		box-sizing: border-box;
		width: 100%;
	}
</style>

<Header {segment}/>

<main>
	<slot></slot>
</main>