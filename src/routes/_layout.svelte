<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<!-- candy framework Scss - Global -->
<style lang="scss" global>
@import "./codyframe/assets/css/style.scss"
</style>

<!--  cody framework - js library -->
<svelte:head>
    <script defer src="codyframe/util.js"></script>
</svelte:head>


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

