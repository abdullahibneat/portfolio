<script>
	import Navbar from "../components/Navbar.svelte"
	import Footer from "../components/Footer.svelte";
</script>

<Navbar />

<main>
	<slot/>
</main>

<Footer />

<style>
	:global(body) {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
</style>