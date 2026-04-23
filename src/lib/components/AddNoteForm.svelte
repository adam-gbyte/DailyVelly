<script>
	let { onAdd } = $props();
	let title = $state('');
	let content = $state('');

	function handleSubmit(e) {
		e.preventDefault();
		if (!title.trim() || !content.trim()) return;

		onAdd({
			id: Date.now(),
			title,
			content,
			date: new Date().toISOString()
		});

		title = '';
		content = '';
	}
</script>

<div id="add-note" class="mx-auto max-w-2xl rounded-3xl bg-white p-8 shadow-sm ring-1 ring-slate-200">
	<h2 class="text-2xl font-bold tracking-tight text-slate-900 mb-6">Tambah Catatan Baru</h2>
	<form onsubmit={handleSubmit} class="space-y-4">
		<div>
			<label for="title" class="block text-sm font-medium text-slate-700">Judul</label>
			<input
				type="text"
				id="title"
				bind:value={title}
				class="mt-1 block w-full rounded-xl border-slate-200 bg-slate-50 px-4 py-3 text-slate-900 focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm shadow-inner"
				placeholder="Judul hari ini..."
				required
			/>
		</div>
		<div>
			<label for="content" class="block text-sm font-medium text-slate-700">Isi Catatan</label>
			<textarea
				id="content"
				rows="4"
				bind:value={content}
				class="mt-1 block w-full rounded-xl border-slate-200 bg-slate-50 px-4 py-3 text-slate-900 focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm shadow-inner"
				placeholder="Ceritakan harimu..."
				required
			></textarea>
		</div>
		<button
			type="submit"
			class="w-full rounded-xl bg-indigo-600 px-4 py-3.5 text-sm font-semibold text-white shadow-lg hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 transition-all active:scale-[0.98]"
		>
			Simpan Catatan
		</button>
	</form>
</div>
