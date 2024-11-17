<script lang="ts">
	import type { AvailableLanguageTag } from '$lib/paraglide/runtime';
	import { languageTag } from '$lib/paraglide/runtime';
	import { i18n } from '$lib/i18n';
	import { page } from '$app/stores';
	import { goto } from '$app/navigation';
	let language = $state('en');

	const flags = {
		en: 'us',
		'pt-br': 'br',
		es: 'es'
	};

	function switchToLanguage(newLanguage: AvailableLanguageTag) {
		language = newLanguage;
		const canonicalPath = i18n.route($page.url.pathname);
		const localisedPath = i18n.resolveRoute(canonicalPath, newLanguage);
		goto(localisedPath);
		console.log(language);
	}
</script>

<div class="group flex w-12 items-end justify-end p-2">
	<!-- main -->
	<div
		class="fi fi-{flags[
			languageTag()
		]} z-50 flex w-8 items-center justify-center p-1 text-white shadow-xl"
	></div>

	<!-- sub left -->
	<button
		aria-label="espanhol"
		onclick={() => switchToLanguage('es')}
		class="absolute flex scale-100 scale-y-0 rounded-full bg-green-300 p-2 text-white transition-all duration-[0.2s] ease-out hover:bg-green-400 hover:p-3 group-hover:-translate-x-16 group-hover:scale-y-100"
	>
		<span class="fi fi-es"></span>
	</button>
	<!-- sub top -->
	<button
		aria-label="english"
		onclick={() => switchToLanguage('en')}
		class="absolute flex scale-x-0 rounded-full bg-blue-300 p-2 text-white transition-all duration-[0.2s] ease-out hover:bg-blue-400 hover:p-3 group-hover:translate-y-16 group-hover:scale-x-100"
	>
		<span class="fi fi-us"></span>
	</button>
	<!-- sub middle -->
	<button
		aria-label="português"
		onclick={() => switchToLanguage('pt-br')}
		class="absolute flex scale-x-0 rounded-full bg-yellow-300 p-2 text-white transition-all duration-[0.2s] ease-out hover:bg-yellow-400 hover:p-3 group-hover:-translate-x-14 group-hover:translate-y-14 group-hover:scale-x-100"
	>
		<span class="fi fi-br"></span>
	</button>
</div>
