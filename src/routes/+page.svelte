<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';

	let visible = $state(false);

	onMount(() => {
		visible = true;
	});
</script>

<svelte:head>
	<title>Vi flytter din side | Wierperia Digital</title>
</svelte:head>

<main class="relative flex min-h-screen flex-col items-center justify-center overflow-hidden bg-[#0a0a0a] px-6 py-12 text-white">
	<!-- Background decoration -->
	<div class="absolute top-0 left-0 -z-10 h-full w-full">
		<div class="absolute top-[-10%] left-[-10%] h-[500px] w-[500px] rounded-full bg-orange-500/10 blur-[120px]"></div>
		<div class="absolute bottom-[-10%] right-[-10%] h-[500px] w-[500px] rounded-full bg-orange-600/5 blur-[120px]"></div>
	</div>

	{#if visible}
		<div class="z-10 flex w-full max-w-2xl flex-col items-center text-center" in:fade={{ duration: 1000 }}>
			<!-- Logo -->
			<div class="mb-12" in:fly={{ y: -20, duration: 800, delay: 200 }}>
				<img src="/wierperia-logo-dark.png" alt="Wierperia Logo" class="h-16 md:h-20" />
			</div>

			<!-- Status Badge -->
			<div 
				class="mb-6 inline-flex items-center gap-2 rounded-full border border-orange-500/20 bg-orange-500/10 px-4 py-1.5 text-sm font-medium text-orange-400"
				in:fly={{ y: 20, duration: 800, delay: 400 }}
			>
				<span class="relative flex h-2 w-2">
					<span class="absolute inline-flex h-full w-full animate-ping rounded-full bg-orange-400 opacity-75"></span>
					<span class="relative inline-flex h-2 w-2 rounded-full bg-orange-500"></span>
				</span>
				Flytning i gang
			</div>

			<!-- Heading -->
			<h1 
				class="mb-6 text-4xl font-bold tracking-tight md:text-6xl"
				in:fly={{ y: 20, duration: 800, delay: 600 }}
			>
				Vi flytter din <span class="text-orange-500">hjemmeside</span>
			</h1>

			<!-- Description -->
			<div 
				class="mb-12 space-y-4 text-lg text-stone-400 md:text-xl"
				in:fly={{ y: 20, duration: 800, delay: 800 }}
			>
				<p>
					Lige nu opdaterer vi DNS-indstillingerne og optimerer din opsætning på vores lynhurtige servere hos Wierperia.
				</p>
				<p class="text-base text-stone-500">
					Processen er næsten færdig. Det tager typisk 1-24 timer for DNS-ændringer at træde helt i kraft på tværs af internettet.
				</p>
			</div>

			<!-- Footer info -->
			<p class="mt-12 text-sm text-stone-600" in:fade={{ delay: 1500 }}>
				&copy; {new Date().getFullYear()} Wierperia Digital
			</p>
		</div>
	{/if}
</main>

<style>
	:global(body) {
		margin: 0;
		background: #0a0a0a;
	}
</style>
