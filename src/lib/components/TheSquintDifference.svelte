<script lang="ts">
	let { className = '' }: { className?: string } = $props();
</script>

<section class={`bg-[var(--color-background)] py-24 lg:py-32 ${className}`}>
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto flex w-full flex-col gap-12 lg:gap-16">
			<div class="flex flex-col gap-4 lg:flex-row lg:items-start lg:gap-8">
				<div class="flex-none lg:w-1/5">
					<div class="flex items-center gap-2">
						<span class="h-2 w-2 flex-none rounded-full bg-gray-900"></span>
						<p class="font-body text-sm font-medium text-gray-900">The Difference</p>
					</div>
				</div>
				<div class="flex-1">
					<h2
						class="font-display text-3xl font-normal leading-tight tracking-tighter text-gray-900 sm:text-4xl lg:text-5xl lg:leading-tight"
					>
						The Squint Difference: Automated,
						<span class="text-gray-500">for visual workflow documentation.</span>
					</h2>
				</div>
			</div>
			<div class="grid grid-cols-1 gap-4 lg:grid-cols-2">
				<div class="flex flex-col justify-between rounded-2xl bg-white p-6 shadow-sm lg:p-8">
					<div>
						<h3 class="font-display text-xl leading-snug tracking-tight text-gray-900">
							From Complex Process to SOP in Minutes.
						</h3>
						<p class="font-body mt-2 text-sm leading-6 text-gray-700">
							Traditional documentation takes days. With Squint, you just record your process, and our
							AI generates a complete guide automatically, ready for your team to use.
						</p>
						<div class="mt-8 space-y-4">
							<div class="flex items-center gap-3">
								<span class="h-1.5 w-1.5 flex-none rounded-full bg-primary-500"></span>
								<span class="font-body text-sm font-medium text-gray-900"
									>Record your screen as you work.</span
								>
							</div>
							<div class="flex items-center gap-3">
								<span class="h-1.5 w-1.5 flex-none rounded-full bg-primary-500"></span>
								<span class="font-body text-sm font-medium text-gray-900"
									>Squint automatically generates a step-by-step guide.</span
								>
							</div>
							<div class="flex items-center gap-3">
								<span class="h-1.5 w-1.5 flex-none rounded-full bg-primary-500"></span>
								<span class="font-body text-sm font-medium text-gray-900"
									>Review, edit, and deploy to your team.</span
								>
							</div>
						</div>
					</div>
					<div class="mt-8">
						<a
							href="#"
							class="group font-body inline-flex items-center gap-2 text-sm font-medium text-gray-900"
						>
							See it in action
							<span aria-hidden="true" class="transition-transform group-hover:translate-x-1">→</span>
						</a>
					</div>
				</div>
				<div class="flex flex-col justify-between rounded-2xl bg-white p-6 shadow-sm lg:p-8">
					<div>
						<h3 class="font-display text-xl leading-snug tracking-tight text-gray-900">
							Built for Manufacturing, Not Generic Office Work.
						</h3>
						<p class="font-body mt-2 text-sm leading-6 text-gray-700">
							Generic video recorders (Loom) and text wikis (Notion) weren't designed for manufacturing processes. Squint's visual recognition technology understands the complexity of hands-on manufacturing work and equipment operation.
						</p>
						<div class="mt-8">
							<div class="flex h-48 items-end justify-between gap-x-4 px-2 text-center">
								<div class="flex h-full w-1/4 flex-col justify-end">
									<p class="font-body text-xs text-gray-700">Low</p>
									<div class="mt-1 h-[40%] w-full rounded-t bg-gray-900"></div>
								</div>
								<div class="flex h-full w-1/4 flex-col justify-end">
									<p class="font-body text-xs text-gray-700">Low</p>
									<div class="mt-1 h-[50%] w-full rounded-t bg-gray-900"></div>
								</div>
								<div class="flex h-full w-1/4 flex-col justify-end">
									<p class="font-body text-xs text-gray-700">Medium</p>
									<div class="mt-1 h-[75%] w-full rounded-t bg-gray-900"></div>
								</div>
								<div class="flex h-full w-1/4 flex-col justify-end">
									<p class="font-body text-xs text-primary-500">High</p>
									<div class="mt-1 h-full w-full rounded-t bg-primary-500"></div>
								</div>
							</div>
							<div class="mt-2 flex justify-between gap-x-4 px-2 text-center">
								<p class="font-body w-1/4 text-xs text-gray-700">Generic Video</p>
								<p class="font-body w-1/4 text-xs text-gray-700">Text Wikis</p>
								<p class="font-body w-1/4 text-xs text-gray-700">Manual Capture</p>
								<p class="font-body w-1/4 text-xs font-medium text-gray-900">Squint</p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>