<script>
	import Navbar from '$lib/components/Navbar.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import Card from '$lib/components/Card.svelte';
	// import AddNoteForm from '$lib/components/AddNoteForm.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let notes = $state([
		{
			id: 1,
			title: 'Awal Perjalanan Baru',
			content: 'Hari ini aku memutuskan untuk mulai mencatat setiap detail kecil dari Vellysia. Semoga blog ini menjadi saksi bisu pertumbuhan Vellysia.',
			date: '2026-04-20T10:00:00Z'
		},
		{
			id: 2,
			title: 'Vellysia bangun di siang hari',
			content: 'Vellysia bangun di siang hari karena tadi malam tidur terlalu larut malam. Semoga Vellysia besok bisa bangun lebih pagi agar bisa menikmati pagi hari dengan lebih baik.',
			date: '2026-04-25T12:55:00Z'
		},
		{
			id: 3,
			title: 'Lorem Ipsum',
			content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
			date: '2026-04-22T18:15:00Z'
		}
	]);

	function handleAddNote(newNote) {
		notes = [newNote, ...notes];
	}
</script>

<Navbar />

<main class="grow">
	<Hero />

	<!-- Notes Grid -->
	<section id="notes" class="bg-slate-50 py-24 sm:py-32">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<div class="mx-auto max-w-2xl text-center">
				<h2 class="text-3xl font-bold tracking-tight text-slate-900 sm:text-4xl">Catatan Harian</h2>
				<p class="mt-4 text-lg leading-8 text-slate-600">
					Kumpulan momen-momen berharga yang tertuangkan dalam kata-kata.
				</p>
			</div>
			
			<div class="mx-auto mt-16 grid max-w-2xl grid-cols-1 gap-x-8 gap-y-12 lg:mx-0 lg:max-w-none lg:grid-cols-3">
				{#each notes as note (note.id)}
					<Card {note} />
				{/each}
			</div>
		</div>
	</section>

	<!-- Add Note Form Section -->
	<!-- <section class="bg-white py-24 sm:py-32">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<AddNoteForm onAdd={handleAddNote} />
		</div>
	</section> -->
</main>

<Footer />
