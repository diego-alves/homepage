<script lang="ts">
	export let y: number;
	const tabs = [
		{ name: 'Projetos', link: '#projects' },
		{ name: 'Sobre', link: '#about' }
	];
</script>

<header
	class={'sticky top-0 z-[10] flex items-center justify-between border border-solid px-6 duration-200' +
		(y > 0 ? ' border-violet-950 bg-slate-950 py-4' : ' border-transparent bg-transparent py-6')}
>
	<h1 class="font-medium">Diego Alves</h1>
	<div class="hidden items-center gap-4 sm:flex">
		{#each tabs as tab, i}
			<a href={tab.link} class="duration-200 hover:text-violet-400">
				<p>{tab.name}</p>
			</a>
		{/each}
	</div>
	<a href="#" target="_blank"
		class="blueShadow overflow-hideen group relative rounded-full bg-white px-5 py-2 text-slate-950"
	>
		<div
			class="absolute right-full top-0 z-0 w-full bg-violet-400 opacity-20 duration-200 group-hover:translate-x-full"
		></div>
		<h4 class="z-9 relative">Entre em contato</h4>
	</a>
</header>
