<script lang="ts">
	import { i18n } from "$lib/i18n";
	import { ParaglideJS } from "@inlang/paraglide-sveltekit";
	import Footer from '../components/Footer.svelte';
	import Header from '../components/Header.svelte';
	import '../app.css';
	export let y: number;
	export let innerWidth = 0;
	export let innerHeight = 0;
	
	function goTop() {
	    document.body.scrollIntoView();
	}
</script>

<ParaglideJS {i18n}>
	<div class="container relative mx-auto flex min-h-screen w-full max-w-[1400px] flex-col text-sm sm:text-base">
		<div
		class={'fixed bottom-0 z-[10] flex w-full p-10 duration-200 ' +
			(y > 0 ? ' opacity-full pointer-events-auto' : ' pointer-events-none opacity-0')}
	>
			<button aria-label="Go To Top" on:click="{goTop}" class="ml-auto grid aspect-square cursor-pointer place-items-center rounded-full bg-slate-900 px-3 text-violet-400 hover:bg-slate-800 sm:px-4">
				<i class="fa-solid fa-arrow-up"></i>
			</button>
		</div>
		<Header {y} />
		<slot />
		<Footer />
	</div>
	
</ParaglideJS>
<svelte:window bind:scrollY="{y}" bind:innerHeight bind:innerWidth></svelte:window>
