<script lang="ts">
  // Types for structuring the sitemap data for better maintainability.
  type Link = {
    href: string;
    text: string;
  };

  type LinkCategory = {
    title: string;
    links: Link[];
  };

  // Props
  let { className = '' }: { className?: string } = $props();

  // State
  // Using $state.raw for static data is a performance optimization,
  // as Svelte won't deeply track changes within the array.
  const sitemap: LinkCategory[] = $state.raw([
    {
      title: 'Product',
      links: [
        { href: '#platform', text: 'Platform' },
        { href: '#use-cases', text: 'Use Cases' },
        { href: '#customers', text: 'Customers' },
      ],
    },
    {
      title: 'Solutions',
      links: [
        { href: '#', text: 'Manufacturing' },
        { href: '#', text: 'Training' },
        { href: '#', text: 'Quality Control' },
      ],
    },
    {
      title: 'Resources',
      links: [
        { href: '#security', text: 'Security' },
        { href: '#', text: 'Documentation' },
        { href: '#', text: 'Contact Us' },
      ],
    },
    {
      title: 'Company',
      links: [
        { href: '#', text: 'About Us' },
        { href: '#', text: 'Careers' },
        { href: '#', text: 'Privacy Policy' },
      ],
    },
  ]);

  // Derived Values
  // Dynamically get the current year for the copyright notice.
  let currentYear = $derived(new Date().getFullYear());
</script>

<footer class={`bg-gray-950 text-gray-50 ${className}`}>
  <div class="mx-auto max-w-[1920px] px-6 lg:px-8">
    <section>
      <div
        class="flex flex-col items-start justify-end gap-7 border-b border-gray-800 py-16 md:flex-row md:items-end md:justify-between lg:py-24"
      >
        <h3 class="font-display text-balance text-left text-4xl md:text-5xl lg:text-6xl">
          Stop Losing Tribal Knowledge. Start Capturing It.
        </h3>
        <a
          href="#"
          class="flex h-12 shrink-0 cursor-pointer items-center justify-center whitespace-nowrap rounded-sm bg-gray-50 px-5 font-medium text-gray-950 transition-colors duration-300 hover:bg-gray-300 active:bg-gray-400"
        >
          <p class="font-body text-base leading-none">Request a Demo</p>
        </a>
      </div>
    </section>
    <section>
      <div class="flex flex-col justify-between py-16 md:grid md:grid-cols-12 lg:py-24">
        <div class="col-span-3 mb-16 flex flex-col justify-between md:mb-0">
          <div class="font-display text-4xl">Squint</div>
        </div>
        <div class="grid w-full grid-cols-2 gap-x-4 gap-y-12 md:col-span-6 md:col-start-7 md:grid-cols-4">
          {#each sitemap as category}
            <div class="flex flex-col gap-4">
              <small class="font-body text-sm text-gray-400">{category.title}</small>
              {#each category.links as link}
                <a
                  href={link.href}
                  class="group flex w-full items-center text-left font-body text-sm font-medium text-gray-50 transition-colors duration-300 hover:text-gray-300"
                >
                  {link.text}<span
                    class="-ml-0.5 opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
                  >
                    →</span
                  >
                </a>
              {/each}
            </div>
          {/each}
        </div>
      </div>
      <div class="flex flex-col-reverse gap-6 py-8 md:flex-row md:items-center md:justify-between">
        <p class="font-body text-balance text-sm text-gray-400">
          Copyright © {currentYear} Squint Technologies Inc. All rights reserved.
        </p>
        <div class="flex items-center gap-4">
          <a
            href="#"
            target="_blank"
            class="font-body text-balance text-sm text-gray-400 transition-colors duration-300 hover:text-gray-50"
            >X</a
          >
          <div class="h-3 w-px bg-gray-800"></div>
          <a
            href="#"
            target="_blank"
            class="font-body text-balance text-sm text-gray-400 transition-colors duration-300 hover:text-gray-50"
            >LinkedIn</a
          >
        </div>
      </div>
    </section>
  </div>
</footer>