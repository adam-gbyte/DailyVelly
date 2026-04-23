<script>
	let isMenuOpen = $state(false);

	const menuItems = [
		{ name: 'Home', href: '#' },
		{ name: 'About', href: '#' },
		{ name: 'Daily Notes', href: '#notes' }
	];
</script>

<nav class="sticky top-0 z-50 border-b border-slate-200/80 bg-white/80 backdrop-blur-md">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<!-- Logo -->
			<div class="flex items-center">
				<a href="/" class="group flex items-center gap-2">
					<div
						class="flex h-8 w-8 items-center justify-center rounded-lg bg-indigo-600 font-bold text-white shadow-lg transition-transform group-hover:scale-110"
					>
						DV
					</div>
					<span class="text-xl font-bold tracking-tight text-slate-800">Daily Velly</span>
				</a>
			</div>

			<!-- Desktop Menu -->
			<div class="hidden md:block">
				<div class="ml-10 flex items-baseline space-x-8">
					{#each menuItems as item}
						<a
							href={item.href}
							class="text-sm font-medium text-slate-600 transition-colors hover:text-indigo-600"
						>
							{item.name}
						</a>
					{/each}
				</div>
			</div>

			<!-- Mobile menu button -->
			<div class="md:hidden">
				<button
					type="button"
					onclick={() => (isMenuOpen = !isMenuOpen)}
					class="inline-flex items-center justify-center rounded-md p-2 text-slate-400 hover:bg-slate-100 hover:text-slate-500 focus:outline-none"
				>
					<span class="sr-only">Open main menu</span>
					<svg
						class="h-6 w-6"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
					>
						{#if isMenuOpen}
							<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
						{:else}
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
							/>
						{/if}
					</svg>
				</button>
			</div>
		</div>
	</div>

	<!-- Mobile Menu -->
	{#if isMenuOpen}
		<div class="md:hidden">
			<div class="space-y-1 px-2 pt-2 pb-3 sm:px-3 bg-white border-b border-slate-100 shadow-xl">
				{#each menuItems as item}
					<a
						href={item.href}
						class="block rounded-md px-3 py-2 text-base font-medium text-slate-600 hover:bg-slate-50 hover:text-indigo-600"
						onclick={() => (isMenuOpen = false)}
					>
						{item.name}
					</a>
				{/each}
			</div>
		</div>
	{/if}
</nav>
