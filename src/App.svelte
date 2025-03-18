<script>
	// https://svelte.dev/examples#svelte-component
	// https://www.w3schools.com/howto/tryit.asp?filename=tryhow_js_full_page_tabs
	import HomePage from './HomePage.svelte';
	import NewsPage from './NewsPage.svelte';
	import Todos from './Todos.svelte';
	import Peekcolor from './peekComponents/Peekcolor.svelte';
	import Navbar from './components/layout/Navbar.svelte';
	
	const webpages = [
		{ name: "Home", component: HomePage, icon: "🏠" },
		{ name: "News", component: NewsPage, icon: "📰" },
		{ name: "Todos", component: Todos, icon: "✓" },
		{ name: "Peekcolor", component: Peekcolor, icon: "🎨" }
	];
	
	// Loads an object in webpages array
	let selectedPage = webpages[0];
	$: console.dir(selectedPage)
	
	// Have to use obj as arg. so value can be a class
	const loadPage = (obj) => selectedPage = obj;

</script>

<Navbar {webpages} {selectedPage} onPageSelect={loadPage} />

<main class="main-content">
	<svelte:component this={selectedPage.component} />
</main>

<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	body {
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		background-color: #f5f5f5;
	}

	.main-content {
		max-width: 1200px;
		margin: 80px auto 0;
		padding: 2rem;
	}
</style>