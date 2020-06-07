<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<!-- candy framework SASS - Global -->
<style lang="scss" global>
@import "./codyframe/assets/css/style.scss"
</style>

<!--<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>-->

<Nav {segment}/>

<main>
	<slot></slot>
</main>

