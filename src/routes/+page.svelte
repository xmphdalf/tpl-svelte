<script lang="ts">
	let visible = $state(false);

	// Show content after a small delay for better animation effect
	setTimeout(() => {
		visible = true;
	}, 100);

	const features = [
		{ icon: '🚀', title: 'SvelteKit 5', desc: 'Latest Svelte with runes & server-side rendering' },
		{
			icon: '🛢️',
			title: 'PostgreSQL + Drizzle',
			desc: 'Modern database setup with type-safe ORM'
		},
		{ icon: '🎨', title: 'TailwindCSS', desc: 'With dark mode & custom animations' },
		{ icon: '🐳', title: 'Docker Ready', desc: 'Containerized PostgreSQL database' }
	];
</script>

<main
	class="container mx-auto flex min-h-screen flex-col items-center justify-center px-4 py-8"
>
	<div class="w-full max-w-4xl space-y-12">
		<div class="space-y-6 text-center">
			<div class="relative inline-block">
				<span class="absolute -top-6 left-0 font-mono text-xs text-accent-500">tpl-svelte</span
				>
				<div class="flex flex-col items-center gap-2">
					<h1
						class="animate-type inline-block overflow-hidden whitespace-nowrap bg-gradient-to-r from-accent-500 to-accent-700 bg-clip-text text-4xl font-bold text-transparent dark:from-accent-400 dark:to-accent-600 md:text-6xl"
					>
						Modern Svelte Template
					</h1>
					<p class="font-mono text-sm text-gray-500 dark:text-gray-400">
						by <a
							href="https://github.com/MihirLathiya510"
							class="text-accent-500 transition-colors hover:text-accent-600"
							>Mihir Lathiya</a
						>
					</p>
				</div>
			</div>

			{#if visible}
				<p
					class="animate-slide-up text-xl text-gray-600 dark:text-gray-300"
					style="animation-delay: 1s;"
				>
					Production-ready template with PostgreSQL, Drizzle ORM, and Dark Mode
				</p>

				<div class="animate-fade-in flex justify-center gap-4" style="animation-delay: 1.5s;">
					<a
						href="https://github.com/MihirLathiya510/tpl-svelte"
						class="flex transform items-center gap-2 rounded-lg bg-accent-500 px-6 py-3 text-white transition-all duration-200 hover:scale-105 hover:bg-accent-600 hover:shadow-lg"
					>
						<span class="text-xl">⭐</span> Use Template
					</a>
					<a
						href="/docs"
						class="flex transform items-center gap-2 rounded-lg bg-gray-200 px-6 py-3 transition-all duration-200 hover:scale-105 hover:bg-gray-300 hover:shadow-lg dark:bg-gray-800 dark:hover:bg-gray-700"
					>
						<span class="text-xl">📖</span> Documentation
					</a>
				</div>

				<div
					class="animate-fade-in mt-16 grid grid-cols-1 gap-6 md:grid-cols-2"
					style="animation-delay: 2s;"
				>
					{#each features as { icon, title, desc }}
						<div
							class="rounded-xl bg-gray-100 p-6 transition-transform duration-200 hover:scale-105 dark:bg-gray-800"
						>
							<span class="mb-4 block text-3xl">{icon}</span>
							<h3 class="mb-2 text-lg font-bold">{title}</h3>
							<p class="text-gray-600 dark:text-gray-300">{desc}</p>
						</div>
					{/each}
				</div>

				<div
					class="animate-fade-in mt-16 rounded-xl bg-gray-100 p-6 dark:bg-gray-800/50"
					style="animation-delay: 2.5s;"
				>
					<h2 class="mb-4 font-mono text-lg">Quick Start</h2>
					<div class="rounded-lg bg-gray-900 p-4 font-mono text-sm text-gray-100">
						<p>npm create svelte@latest my-app -- --template https://github.com/user/tpl-svelte</p>
						<p>cd my-app</p>
						<p>npm install</p>
						<p>npm run dev</p>
					</div>
				</div>
			{/if}
		</div>
	</div>
</main>

<style>
	/* Ensure animations only play once */
	.animate-type {
		animation-fill-mode: forwards;
	}
</style>
