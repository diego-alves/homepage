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
			name: 'um desenvolvedor autodidata',
			description:
				'Muito do que aprendi foi sozinho usando recursos online gratuitos e me apaixonei pela resolução de problemas envolvidas no desenvolvimento e engenharia de novas tecnologias inovadoras. Comecei com Java e evoluí minha base de conhecimento para incluir Node.js, Python, Golang, serviços em nuvem e muito mais.'
		},
		{
			name: 'habilidoso em lógica e estrutura de dados',
			description:
				'Tenho um forte domínio em lógica e estruturas de dados, o que me permite criar sistemas eficientes e escaláveis. Esse conhecimento é essencial para manipular e organizar informações de forma otimizada, facilitando tarefas como ordenação e busca de dados. Assim, consigo escrever códigos mais rápidos e limpos, melhorando o desempenho e garantindo que a aplicação seja fácil de escalar.'
		},
		{
			name: 'um excelente comunicador',
			description:
				'A comunicação é fundamental e é um valor essencial para mim. Acredito em transparência e comunicação construtiva acima de tudo. Isso me ajuda a desenvolver relacionamentos profundos e garante minha eficácia e produtividade em qualquer ambiente de trabalho e com qualquer equipe.'
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
				<h4 class="z-9 relative">Entre em contato &rarr;</h4>
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
			<h6 class="text-large sm:text-xl md:text-2xl">Um pouco de onde trabalhei.</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				Curioso para <span class="poppins text-violet-400">ver</span> meu trabalho?
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
					O PagBank é uma plataforma digital de pagamentos e serviços financeiros, voltada para
					atender pessoas físicas e pequenas empresas com soluções como contas digitais, cartões,
					empréstimos e investimentos. Para garantir alta <strong class="text-violet-400"
						>disponibilidade, segurança e escalabilidade</strong
					>
					para milhões de transações diárias, mantendo uma experiência de usuário fluida sua infraestrutura
					inclue o uso de
					<strong class="text-violet-400">centenas de microsserviços</strong>
					para modularidade e a aplicação de arquiteturas distribuídas em linguagens como
					<strong class="text-violet-400">Java & Kotlin</strong>.
				</p>
			</Step>
			<Step step={steps[1]}>
				<p>
					A Chiper é uma startup colombiana que atua como plataforma de compras e distribuição para
					pequenos comerciantes e mercearias locais na América Latina onde o principal desafio é
					criar uma infraestrutura robusta que suporte operações complexas de logística, controle de
					estoque e pedidos em tempo real e para isso usamos utiliza tecnologias como <strong
						class="text-violet-400">Node.js & Python</strong
					>
					para o desenvolvimento back-end,
					<strong class="text-violet-400">React & React Native</strong> para o front-end e mobile.
				</p>
			</Step>
			<Step step={steps[2]}>
				<p>
					A AppCare também é uma startup colombiana mas que atua facilitando o agendamento,
					realização e acompanhamento de consultas, conectando médicos e pacientes em uma plataforma
					digital. Utilizando tecnologias como <strong class="text-violet-400">Node.js</strong> para
					o back-end, junto a framework de front-end
					<strong class="text-violet-400">Next.js</strong>, essa aplicação pode oferecer
					funcionalidades de vídeo-chamadas, notificações em tempo real, e gestão de prontuários
					eletrônicos. Seu desenvolvimento com ferramentas como
					<strong class="text-violet-400">Twilio, Agora, Algolia e models de IA</strong> para apoio de
					diagnotiscos.
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
			<h6 class="text-large sm:text-xl md:text-2xl">Quer saber mais?</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				Um pouco <span class="poppins text-violet-400">sobre</span> mim.
			</h3>
		</div>
		<p class="poppins mx-auto text-lg font-semibold sm:text-xl md:text-2xl">Eu sou . . .</p>
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
			O Pacote <span class="text-violet-400">Completo</span>
		</h5>
		<div class="mx-auto flex w-full max-w-[800px] flex-col gap-10 overflow-x-scroll">
			<table class="rounded bg-white text-center text-slate-700">
				<thead class={'border-b border-solid border-slate-200  '}>
					<tr class="">
						<th></th>
						<th class="whitespace-nowrap p-2 px-4">Cadidato #1</th>
						<th class="whitespace-nowrap p-2 px-4">Cadidato #2</th>
						<th class="whitespace-nowrap p-2 px-4">Cadidato #3</th>
						<th class="whitespace-nowrap bg-violet-700 p-4 px-8 text-white">Eu</th>
					</tr>
				</thead>
				<tbody>
					<tr class="border-b border-solid border-slate-200">
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>Dedicação</td
						>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
					<tr class="border-b border-solid border-slate-200">
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>Pensamento crítico</td
						>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
					<tr>
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>Habilidades Interpessoais</td
						>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
					<tr class="border-t border-solid border-slate-200">
						<td class="border-r border-solid border-white py-4 pl-4 pr-8 text-sm font-semibold"
							>Habilidade em Programação</td
						>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-xmark text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-slate-500"></i></td>
						<td><i class="fa-solid fa-check text-green-500"></i></td>
					</tr>
				</tbody>
			</table>
		</div>
		<div class="mx-auto -mt-12 italic opacity-50 sm:hidden">
			<p>Role para ver mais &rarr;</p>
		</div>
		<p class="mx-auto">Então, porque não investir?</p>
	</section>
</main>
