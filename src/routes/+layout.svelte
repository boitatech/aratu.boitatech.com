<script>
	import NavBar from '../components/NavBar/index.svelte'
	import '../styles.css';
	import Footer from '../components/Footer/index.svelte'
</script>

<div class="app">
	<NavBar/>

	<main>
		<slot />
	</main>

	<Footer/>
</div>

<style global>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		width: 100%;
		display: grid;
		justify-items: center;
	}
</style>
