<script lang="ts">
	import Step from './Step.svelte';
	import * as m from '$lib/paraglide/messages.js';

	let steps = [
		{
			name: 'PagBank',
			icon: 'fa-solid fa-credit-card',
			href: 'https://pagbank.com'
		},
		{
			name: 'Chiper',
			icon: 'fa-solid fa-cart-shopping',
			href: 'https://chiper.co'
		},
		{
			name: 'Care',
			icon: 'fa-solid fa-stethoscope',
			href: 'https://appcare.com.co'
		}
	];

	let benefits = [
		{
			metric: '10x',
			name: m.benefits_auto_title(),
			description: m.benefits_auto_description()
		},
		{
			name: m.benefits_skill_title(),
			description: m.benefits_skill_description()
		},
		{
			name: m.benefits_comm_title(),
			description: m.benefits_comm_description()
		}
	];
</script>

<main class="flex flex-1 flex-col p-4">
	<section id="introPage" class="grid grid-cols-1 gap-10 py-8 sm:py-14 lg:grid-cols-2">
		<div class="flex flex-col gap-6 text-center md:gap-8 lg:justify-center lg:gap-10 lg:text-left">
			<h2 class="text-4xl font-semibold sm:text-5xl md:text-6xl">
				{@html m.hello({ name: 'Diego', surname: 'Alves' })}
			</h2>
			<p class="text-base sm:text-lg md:text-xl">
				{@html m.sub_hello()}
			</p>
			<button
				class="blueShadow poppins group relative mx-auto overflow-hidden rounded-full bg-white px-6 py-3 text-base text-slate-950 sm:text-lg md:text-xl lg:ml-0 lg:mr-auto"
			>
				<div
					class="absolute right-full top-0 z-0 h-full w-full bg-violet-400 opacity-20 duration-200 group-hover:translate-x-full"
				></div>
				<h4 class="z-9 relative">{m.contact()} &rarr;</h4>
			</button>
		</div>
		<div class="relative grid place-items-center shadow-2xl">
			<img
				src={'https://i.ibb.co/0rjDd9X/profile.png'}
				alt="Profile"
				class="z-[2] max-h-[70vh] object-cover"
			/>
		</div>
		<!-- <div  class="flex p-0.5 relative max-w-[700px] w-full mx-auto">
            <div
                class="absolute inset-0 overflow-hidden rounded-md flex items-center justify-center"
            >
                <div
                    class="bg-gradient-to-r absolute inset-[-20px]  from-violet-800 to-indigo-800 specialSpin"
                />
            </div>

            <img
                src={"images/zetane-engine.jpeg"}
                alt="Zetane Engine"
                class="w-full h-full object-cover z-[2]"
            />
        </div> -->
	</section>
	<section class="flex flex-col gap-24 py-20 lg:py-32" id="projects">
		<div class="flex flex-col gap-2 text-center">
			<h6 class="text-large sm:text-xl md:text-2xl">{m.a_bit_where_worked()}</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				{@html m.curious_to_see_my_work()}
			</h3>
		</div>
		<!-- <a
			href="https://www.youtube.com/watch?v=dQw4w9WgXcQ"
			target="_blank"
			class="mx-auto -mb-4 -mt-10 flex items-center gap-2 rounded-md border border-solid border-white px-4 py-2 duration-200 hover:border-violet-700 sm:-mb-0"
		>
			<i class="fa-regular fa-circle-play" />
			<p>Watch the video</p>
		</a> -->
		<div class="grid grid-cols-1 gap-12 lg:grid-cols-3 lg:gap-10">
			<Step step={steps[0]}>
				<p>
					{@html m.work_pagbank()}
				</p>
			</Step>
			<Step step={steps[1]}>
				<p>
					{@html m.work_chiper()}
				</p>
			</Step>
			<Step step={steps[2]}>
				<p>
					{@html m.work_care()}
				</p>
			</Step>
		</div>
	</section>
	<section
		id="about"
		class="relative flex flex-col gap-16 py-20 pt-10 sm:gap-20 md:gap-24 lg:py-32 lg:pt-16"
	>
		<!-- <div class="z-[-1] bg-violet-950 w-screen left-1/2 -translate-x-1/2 top-0 h-full absolute"> </div> -->
		<div
			class="relative flex flex-col gap-2 py-4 text-center before:absolute before:left-0 before:top-0 before:h-1.5 before:w-2/3 before:bg-violet-700 after:absolute after:bottom-0 after:right-0 after:h-1.5 after:w-2/3 after:bg-violet-700"
		>
			<h6 class="text-large sm:text-xl md:text-2xl">{m.know_more()}</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				{@html m.a_bit_about_me()}
			</h3>
		</div>
		<p class="poppins mx-auto text-lg font-semibold sm:text-xl md:text-2xl">{m.i_am()} . . .</p>
		<div class="mx-auto flex w-full max-w-[800px] flex-col gap-20">
			{#each benefits as benefit, index}
				<!-- <div class="flex flex-col gap-2 mx-auto">
                    <div class="flex items-end gap-4">
                        <p
                            class="poppins text-6xl sm:text-7xl md:text-8xl text-slate-500 font-medium"
                        >
                            {benefit.metric}
                        </p>
                        <p
                            class="text-xl sm:text-2xl md:text-3xl capitalize pb-2"
                        >
                            {benefit.name}
                        </p>
                    </div>
                    <p class="text-center italic">- {benefit.description}</p>
                </div> -->
				<div class="flex gap-6 sm:gap-8">
					<p class="poppins text-4xl font-semibold text-slate-500 sm:text-5xl md:text-6xl">
						0{index + 1}
					</p>
					<div class="flex flex-col gap-6 sm:gap-8">
						<h3 class="text-2xl sm:text-3xl md:text-5xl">
							{benefit.name}
						</h3>
						<p>{benefit.description}</p>
					</div>
				</div>
			{/each}
		</div>
		<h5 class={' poppins text-center text-2xl font-semibold sm:text-3xl '}>
			{@html m.complete_package()}
		</h5>
		<div class="mx-auto flex w-full max-w-[800px] flex-col gap-10 overflow-x-scroll">
			<table class="rounded bg-white text-center text-slate-700">
				<thead class={'border-b border-solid border-slate-200  '}>
					<tr class="">
						<th></th>
						<th class="whitespace-nowrap p-2 px-4">{m.candidate()} #1</th>
						<th class="whitespace-nowrap p-2 px-4">{m.candidate()} #2</th>
						<th class="whitespace-nowrap p-2 px-4">{m.candidate()} #3</th>
						<th class="whitespace-nowrap bg-violet-700 p-4 px-8 text-white">{m.me()}</th>
					</tr>
				</thead>
				<tbody>
					<tr class="border-b border-solid border-slate-200">
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>{m.dedication()}</td
						>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
					<tr class="border-b border-solid border-slate-200">
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>{m.critical_thinking()}</td
						>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
					<tr>
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>{m.interpersonal_skills()}</td
						>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
					<tr class="border-t border-solid border-slate-200">
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>{m.programming_skills()}</td
						>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
				</tbody>
			</table>
		</div>
		<div class="mx-auto -mt-12 italic opacity-50 sm:hidden ">
			<p>Role para ver mais &rarr;</p>
		</div>
		<p class="mx-auto">{m.invest()}</p>
	</section>
</main>
