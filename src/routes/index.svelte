<script>
	import Section from "../components/Section.svelte";

	export let name = "World"
</script>

<svelte:head>
	<title>Sapper</title>
</svelte:head>

<Section>
	<h1>Hello, {name}</h1>
</Section>