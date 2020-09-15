<script>
	import Nav from '../components/Nav.svelte';
    import { onMount } from "svelte";
	export let segment;

  let codyFrameScripts = "";
  onMount(async () => {
    // ---- To mount the CodyFrame scripts ----
    codyFrameScripts = "codyframe/util.js";
  });
</script>

<!-- Codyframework Global Scss -->
<style lang="scss" global>
@import "./codyframe/assets/css/style.scss"
</style>

<!--  cody framework - js libraries -->
<svelte:head>
    <script defer src={codyFrameScripts}></script>
</svelte:head>

<Nav {segment}/>

<main>
	<slot></slot>
</main>

