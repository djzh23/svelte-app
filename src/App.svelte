<script>
	import HomePage from './HomePage.svelte';
	import Todos from './Todos.svelte';
	import Peekcolor from './peekComponents/Peekcolor.svelte';
	import Galerie from './Galerie.svelte';
	import Chatroom from './Chatroom.svelte';
	import {auth,googleProvider} from "./firebase";
	import {authState} from "rxfire/auth";
	import Profile from "./Profile.svelte";
	
	export let user;

	const unsubscribe = authState(auth).subscribe(usr => user = usr);

	function login(){
		auth.signInWithPopup(googleProvider);
		
	}
	function logout(){
		auth.signOut();
	}

	const webpages = [
		{ name: "Home", component: HomePage },
		{ name: "Galerie", component: Galerie },
		{ name: "Todos", component: Todos },
		{ name: "PKcolor", component: Peekcolor },
		{ name: "Chat", component: Chatroom }
	];
	
	// Loads an object in webpages array
	let selectedPage = webpages[0];
	$: console.dir(selectedPage)
	
	// Have to use obj as arg. so value can be a class
	const loadPage = (obj) => selectedPage = obj;

</script>

{#if user } 
	<!-- Loaded component/webpage -->
	<button on:click={logout} style=" background-color: yellow;"> LOGOUT  </button>	
	<div style="text-align: right;">
		<Profile {...user}/>
	</div>
{/if}

<header class="container">  
{#if user} 
	{#each webpages as webpageObj}
		<button class="tablink" 
						title={webpageObj.name}
						on:click={() => loadPage(webpageObj)}>{webpageObj.name}</button>
	{/each}
	<svelte:component this={selectedPage.component}/>
{:else}
<div class="login-form" style="text-align: center;">
	<button on:click={login} style=" background-color: grey;">
		<i class="fa fa-google"></i>
		Sign In with Google
	</button>
</div>
{/if}
</header>




<style>

	* {box-sizing: border-box}

	/* Style tab links */
	.tablink {
		background-color: #555;
		color: white;
		float: left;
		border: none;
		outline: none;
		border: 0px solid #444;
		border-radius: 0;
		cursor: pointer;
		padding: 14px 16px;
		font-size: 17px;
		/*------------------- Menu TABS --------------------*/
		width: 20%;
		/* width: 16.66%; */
	}

	.tablink:hover {
		background-color: #777;
	}

	.container {
		position: relative;
		}

	.topright {
		position: absolute;
		top: 50px;
		left: 35%;
		font-size: 18px;
		}


</style>

