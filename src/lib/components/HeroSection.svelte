<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();

	// State
	let isPlaying = $state(false);

	// Functions
	function playVideo() {
		isPlaying = true;
	}

	function handleKeydown(e: KeyboardEvent) {
		if (e.key === 'Enter' || e.key === ' ') {
			e.preventDefault();
			playVideo();
		}
	}
</script>

<section
	id="hero"
	class="flex flex-col items-center justify-center gap-6 bg-primary-950 pt-24 lg:pt-32 {className}"
>
	<div class="flex w-full flex-col items-center pt-6">
		<div class="flex flex-col items-center gap-8">
			<div class="flex flex-col items-center gap-6 px-6 text-center">
				<div>
					<h1
						class="font-display text-6xl font-medium text-primary-50 text-balance md:text-7xl lg:text-8xl"
					>
						Visual Knowledge.
					</h1>
					<h1
						class="font-display text-6xl font-medium text-primary-50 text-balance md:text-7xl lg:text-8xl"
					>
						Instantly Captured.
					</h1>
				</div>
				<p class="font-body mx-auto max-w-xl text-lg font-normal text-primary-300 text-balance">
					Squint automatically creates step-by-step guides from screen recordings, preserving your
					team's tribal knowledge before it walks out the door.
				</p>
			</div>
			<a
				class="flex h-12 cursor-pointer items-center justify-center rounded-md bg-primary-50 px-5 text-base font-medium text-primary-950 transition-colors duration-300 ease-in-out hover:bg-primary-200 active:bg-primary-300"
				href="#"
			>
				<p class="whitespace-nowrap leading-none">Request a Demo</p>
			</a>
		</div>

		<div class="mx-auto mt-16 w-full max-w-screen-2xl px-6 lg:px-8">
			<div class="relative col-span-full h-fit">
				<div class="mx-auto">
					<div class="flex flex-col">
						<div class="relative aspect-video w-full overflow-hidden rounded-md">
							{#if !isPlaying}
								<div
									role="button"
									tabindex="0"
									aria-label="Play Video"
									class="group/videotrigger relative h-full w-full cursor-pointer"
									onclick={playVideo}
									onkeydown={handleKeydown}
								>
									<!-- Visual representation of the play button -->
									<div
										class="pointer-events-none absolute left-1/2 top-1/2 z-20 -translate-x-1/2 -translate-y-1/2 backdrop-blur-sm"
									>
										<div
											class="flex h-14 w-14 items-center overflow-hidden rounded-full bg-primary-800/50 transition-all duration-500 ease-in-out group-hover/videotrigger:bg-primary-800/60 md:h-[72px] md:w-[72px]"
										>
											<div
												class="flex translate-x-4 items-center gap-1 transition-transform duration-500 ease-in-out md:translate-x-5"
											>
												<div
													class="relative h-full w-full transition-opacity duration-500 ease-in-out"
												>
													<svg
														class="h-6 w-6 text-primary-50"
														viewBox="0 0 24 24"
														fill="currentColor"
														xmlns="http://www.w3.org/2000/svg"
													>
														<path
															d="M6.32261 2.24239C7.33331 1.64333 8.66669 1.64333 9.67739 2.24239L19.0263 7.9188C20.037 8.51786 20.6774 9.61168 20.6774 10.8119V13.1881C20.6774 14.3883 20.037 15.4821 19.0263 16.0812L9.67739 21.7576C8.66669 22.3567 7.33331 22.3567 6.32261 21.7576L4.97372 20.9188C3.96302 20.3198 3.32261 19.2259 3.32261 18.0257V5.97428C3.32261 4.77406 3.96302 3.68024 4.97372 3.08118L6.32261 2.24239Z"
														></path>
													</svg>
												</div>
											</div>
										</div>
									</div>
									<!-- Thumbnail image -->
									<div class="absolute inset-0 z-10 bg-black">
										<img
											alt="Video showing Squint automatically capturing a work process on screen."
											src="https://www.ledr.com/colours/white.jpg"
											class="h-full w-full object-cover"
										/>
									</div>
								</div>
							{:else}
								<iframe
									class="h-full w-full"
									src="https://www.youtube.com/embed/VIDEO_ID?autoplay=1&rel=0&modestbranding=1"
									title="Squint Product Demo"
									frameborder="0"
									allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
									allowfullscreen
								></iframe>
							{/if}
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>