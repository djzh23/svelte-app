<script>
	export let title = '';
	export let subtitle = '';
	export let icon = '';
</script>

<div class="card">
	{#if title || icon}
		<div class="card-header">
			{#if icon}
				<span class="icon">{icon}</span>
			{/if}
			{#if title}
				<h3>{title}</h3>
			{/if}
		</div>
	{/if}
	{#if subtitle}
		<p class="subtitle">{subtitle}</p>
	{/if}
	<div class="card-content">
		<slot></slot>
	</div>
</div>

<style>
	.card {
		background: white;
		border-radius: 8px;
		box-shadow: 0 2px 4px rgba(0,0,0,0.1);
		padding: 1.5rem;
		margin-bottom: 1rem;
		transition: transform 0.3s ease, box-shadow 0.3s ease;
	}

	.card:hover {
		transform: translateY(-2px);
		box-shadow: 0 4px 8px rgba(0,0,0,0.15);
	}

	.card-header {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		margin-bottom: 1rem;
	}

	.card-header h3 {
		margin: 0;
		font-size: 1.25rem;
		color: #333;
	}

	.subtitle {
		color: #666;
		font-size: 0.9rem;
		margin-bottom: 1rem;
	}

	.card-content {
		color: #444;
	}

	.icon {
		font-size: 1.5rem;
	}
</style> 