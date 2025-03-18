<script>
	export let webpages = [];
	export let selectedPage;
	export let onPageSelect;
</script>

<nav class="navbar">
	<div class="nav-content">
		<div class="logo">My App</div>
		<div class="nav-links">
			{#each webpages as webpageObj}
				<button 
					class="nav-link {selectedPage.name === webpageObj.name ? 'active' : ''}"
					on:click={() => onPageSelect(webpageObj)}
				>
					<span class="icon">{webpageObj.icon}</span>
					{webpageObj.name}
				</button>
			{/each}
		</div>
	</div>
</nav>

<style>
	.navbar {
		background-color: #ffffff;
		box-shadow: 0 2px 4px rgba(0,0,0,0.1);
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		z-index: 1000;
	}

	.nav-content {
		max-width: 1200px;
		margin: 0 auto;
		padding: 1rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.logo {
		font-size: 1.5rem;
		font-weight: bold;
		color: #333;
	}

	.nav-links {
		display: flex;
		gap: 1rem;
	}

	.nav-link {
		background: none;
		border: none;
		padding: 0.5rem 1rem;
		cursor: pointer;
		font-size: 1rem;
		color: #666;
		display: flex;
		align-items: center;
		gap: 0.5rem;
		border-radius: 4px;
		transition: all 0.3s ease;
	}

	.nav-link:hover {
		background-color: #f0f0f0;
		color: #333;
	}

	.nav-link.active {
		background-color: #e3f2fd;
		color: #1976d2;
	}

	.icon {
		font-size: 1.2rem;
	}
</style> 