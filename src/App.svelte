<script>
	import HomePage from './HomePage.svelte';
	import Todos from './Todos.svelte';
	import Peekcolor from './peekComponents/Peekcolor.svelte';
	import Galerie from './Galerie.svelte';

	const webpages = [
		{ name: "Home", component: HomePage },
		{ name: "Galerie", component: Galerie },
		{ name: "Todos", component: Todos },
		{ name: "Peekcolor", component: Peekcolor }
	];
	
	// Loads an object in webpages array
	let selectedPage = webpages[0];
	$: console.dir(selectedPage)
	
	// Have to use obj as arg. so value can be a class
	const loadPage = (obj) => selectedPage = obj;

</script>


{#each webpages as webpageObj}
	<button class="tablink" 
					title={webpageObj.name}
					on:click={() => loadPage(webpageObj)}>{webpageObj.name}</button>
{/each}


<!-- Loaded component/webpage -->
<svelte:component this={selectedPage.component} />


<style>
	* {box-sizing: border-box}

	/* Style tab links */
	.tablink {
		background-color: #555;
		color: white;
		float: left;
		border: none;
		outline: none;
		border: .5px solid #444;
		border-radius: 0;
		cursor: pointer;
		padding: 14px 16px;
		font-size: 17px;
		width: 25%;
	}

	.tablink:hover {
		background-color: #777;
	}


</style>