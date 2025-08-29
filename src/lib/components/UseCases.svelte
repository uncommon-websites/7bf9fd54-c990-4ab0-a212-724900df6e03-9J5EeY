<script lang="ts">
	// Types
	type UseCase = {
		id: string;
		title: string;
		description: string;
		image: string;
	};

	// Props
	let { className = '' }: { className?: string } = $props();

	// State
	const useCases: UseCase[] = $state.raw([
		{
			id: 'new-hire-onboarding',
			title: 'New Hire Onboarding',
			description: 'Get new team members up to speed in record time with clear, visual work instructions.',
			image: 'https://images.unsplash.com/photo-1556740738-b6a63e27c4df?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600'
		},
		{
			id: 'standardizing-workflows',
			title: 'Standardizing Workflows',
			description: 'Ensure every task is performed the same way, every time, reducing errors and improving quality.',
			image: 'https://images.unsplash.com/photo-1522202176988-66273c2fd55f?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600'
		},
		{
			id: 'quality-control-checks',
			title: 'Quality Control Checks',
			description: 'Document and verify quality checks with visual proof, creating an auditable trail of compliance.',
			image: 'https://images.unsplash.com/photo-1516321497487-e288fb19713f?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600'
		},
		{
			id: 'capturing-tribal-knowledge',
			title: 'Capturing Tribal Knowledge',
			description: 'Preserve the expertise of your most experienced workers before they retire or leave.',
			image: 'https://images.unsplash.com/photo-1499750310107-5fef28a66643?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600'
		},
		{
			id: 'safety-compliance',
			title: 'Safety & Compliance',
			description: 'Create easy-to-follow safety procedures and compliance checklists that are always accessible.',
			image: 'https://images.unsplash.com/photo-1581092921461-e71d50a13f33?ixlib=rb-4.0.3&q=85&fm=jpg&crop=entropy&cs=srgb&w=3600'
		}
	]);

	let activeUseCaseId = $state(useCases[0].id);
	let listItems: (HTMLDivElement | null)[] = $state.raw(Array(useCases.length).fill(null));
	let indicatorStyle = $state('top: 0.5rem; transform: translateY(0);');

	// Derived
	let activeUseCase = $derived(useCases.find((uc) => uc.id === activeUseCaseId)!);

	// Functions
	function selectUseCase(id: string) {
		activeUseCaseId = id;
	}

	// Effects
	$effect(() => {
		const activeIndex = useCases.findIndex((uc) => uc.id === activeUseCaseId);
		const activeElement = listItems[activeIndex];

		if (activeElement) {
			const buttonEl = activeElement.querySelector('button');
			if (buttonEl) {
				const newTop = activeElement.offsetTop + buttonEl.offsetHeight / 2;
				indicatorStyle = `top: ${newTop}px; transform: translateY(-50%);`;
			}
		}
	});
</script>

<section class="bg-[var(--color-background)] py-24 lg:py-32 {className}">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="flex flex-col gap-10 lg:gap-16">
			<header class="flex flex-col gap-6 lg:flex-row lg:items-start lg:justify-between">
				<div class="flex items-center gap-2">
					<span class="h-2 w-2 rounded-full bg-gray-900"></span>
					<span class="font-body text-sm font-medium uppercase tracking-wider text-gray-900"
						>Use Cases</span
					>
				</div>
				<div class="flex flex-col gap-6 lg:w-3/5">
					<h2 class="font-display text-4xl leading-tight text-gray-900 lg:text-5xl">
						Solve Your Biggest <span class="text-gray-500">Operational Challenges</span>
					</h2>
					<p class="font-body max-w-md text-lg leading-relaxed text-gray-700">
						Empower your operations managers to standardize processes, reduce training time, and
						preserve critical knowledge.
					</p>
				</div>
			</header>
			<div class="flex flex-col gap-8 lg:flex-row">
				<aside class="flex w-full flex-col lg:w-1/3">
					<div class="bg-gray-50 p-8 lg:p-10">
						<div class="relative flex flex-col gap-5">
							<span
								class="absolute -left-2 h-1.5 w-1.5 rounded-full bg-primary-500 ring-4 ring-primary-500/20 transition-all duration-300 ease-in-out"
								style={indicatorStyle}
							></span>

							{#each useCases as useCase, i (useCase.id)}
								<div bind:this={listItems[i]}>
									<button
										onclick={() => selectUseCase(useCase.id)}
										class="w-full text-left font-display text-2xl transition-colors duration-200"
										class:text-primary-500={activeUseCaseId === useCase.id}
										class:text-gray-900={activeUseCaseId !== useCase.id}
										class:hover:text-primary-500={activeUseCaseId !== useCase.id}
									>
										{useCase.title}
									</button>
									{#if activeUseCaseId === useCase.id}
										<p class="font-body mt-2 text-gray-700">
											{useCase.description}
										</p>
									{/if}
								</div>
							{/each}
						</div>
					</div>
					<div class="p-8 lg:p-10">
						<a href="#" class="group inline-flex items-center gap-3 text-gray-900">
							<span
								class="font-body border-b-2 border-gray-200 transition-colors group-hover:border-gray-900"
								>Explore all use cases</span
							>
							<span
								class="flex h-8 w-8 items-center justify-center rounded-full bg-gray-200 transition-transform group-hover:scale-110"
								>→</span
							>
						</a>
					</div>
				</aside>
				<main class="w-full lg:w-2/3">
					<div
						class="h-[400px] w-full rounded-2xl bg-gray-800 bg-cover bg-center transition-all duration-300 lg:h-full"
						style:background-image="url({activeUseCase.image})"
						aria-label="Image for {activeUseCase.title} use case"
						role="img"
					></div>
				</main>
			</div>
		</div>
	</div>
</section>