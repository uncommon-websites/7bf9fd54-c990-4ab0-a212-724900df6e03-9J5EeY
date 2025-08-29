<script lang="ts">
  // Types
  type Logo = {
    src: string;
    alt: string;
  };

  // Props
  let { className = '' }: { className?: string } = $props();

  // State
  // The list of logos is defined as a raw, non-reactive array for performance,
  // as it's static content. It's duplicated in the template for the seamless scroll effect.
  const logos: Logo[] = $state.raw([
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' },
    { src: 'https://www.ledr.com/colours/white.jpg', alt: 'customer logo' }
  ]);
</script>

<section id="customers" class={`overflow-hidden bg-neutral-950 ${className}`}>
  <div class="flex flex-col items-center gap-8 py-24 lg:py-32">
    <div class="flex flex-col items-center gap-6 px-6 text-center">
      <h3
        class="font-display text-balance text-[32px] font-medium leading-tight -tracking-tight text-neutral-200 md:text-[40px]"
      >
        Trusted by Leading Manufacturers
      </h3>
    </div>
    <div class="relative flex w-full max-w-[2000px] flex-col items-center gap-4">
      <div
        class="absolute left-0 top-0 z-10 h-[78px] w-[20vw] bg-gradient-to-r from-neutral-950 to-transparent md:w-[10vw]"
      ></div>
      <div class="w-full overflow-hidden">
        <ul class="flex w-max animate-scroll">
          {#each [...logos, ...logos] as logo}
            <li class="mx-6 flex h-[78px] flex-shrink-0 list-none items-center">
              <img
                alt={logo.alt}
                loading="eager"
                class="h-auto max-h-full w-auto"
                src={logo.src}
              />
            </li>
          {/each}
        </ul>
      </div>
      <div
        class="absolute right-0 top-0 z-10 h-[78px] w-[20vw] bg-gradient-to-l from-neutral-950 to-transparent md:w-[10vw]"
      ></div>
    </div>
  </div>
</section>

<style>
  @keyframes scroll {
    to {
      /* The list is duplicated, so we translate by 50% of the total width.
         The margin `mx-6` is 1.5rem on each side, totaling 3rem.
         We add half of that margin (1.5rem) to the translation to ensure
         the spacing is perfect when the animation loops. */
      transform: translate(calc(-50% - 1.5rem));
    }
  }
  .animate-scroll {
    animation: scroll 60s linear infinite;
  }
</style>