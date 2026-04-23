<script>
	let { note } = $props();
</script>

<div class="group relative flex flex-col items-start justify-between rounded-2xl bg-white p-6 shadow-sm ring-1 ring-slate-200 transition-all hover:shadow-xl hover:-translate-y-1">
	<div class="flex items-center gap-x-4 text-xs">
		<time datetime={note.date} class="text-slate-500">
			{new Date(note.date).toLocaleDateString('id-ID', { day: 'numeric', month: 'long', year: 'numeric' })}
		</time>
		<span class="relative z-10 rounded-full bg-slate-50 px-3 py-1.5 font-medium text-slate-600 hover:bg-slate-100">Daily Log</span>
	</div>
	<div class="group relative">
		<h3 class="mt-3 text-lg font-semibold leading-6 text-slate-900 group-hover:text-indigo-600">
			<a href="#">
				<span class="absolute inset-0"></span>
				{note.title}
			</a>
		</h3>
		<p class="mt-5 line-clamp-3 text-sm leading-6 text-slate-600">
			{note.content}
		</p>
	</div>
	<div class="relative mt-8 flex items-center gap-x-4">
		<div class="text-sm leading-6">
			<p class="font-semibold text-slate-900">
				<a href="#">
					<span class="absolute inset-0"></span>
					Velly
				</a>
			</p>
		</div>
	</div>
</div>
