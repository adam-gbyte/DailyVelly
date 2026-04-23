<script>
	import './layout.css';
	let { children } = $props();
</script>

<svelte:head>
	<title>Daily Velly - Catatan Harian</title>
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
</svelte:head>

<div class="min-h-screen flex flex-col">
	{@render children()}
</div>
