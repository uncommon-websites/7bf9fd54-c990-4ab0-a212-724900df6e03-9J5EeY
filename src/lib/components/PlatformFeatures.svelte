<script lang="ts">
  // Types
  type Feature = {
    step: string;
    title: string;
    description: string;
    imageUrl: string;
    imageAlt: string;
    layout: "normal" | "reversed";
  };

  // Props
  let { className = "" }: { className?: string } = $props();

  // Component's static content, structured for maintainability and readability.
  // This keeps the content within the component, avoiding over-abstraction into props.
  const features: Feature[] = [
    {
      step: "Capture",
      title: "Record Any Process, Automatically",
      description:
        "Simply perform a task on screen. Squint’s visual recognition technology documents every critical step, click, and action without interrupting your workflow.",
      imageUrl: "https://www.ledr.com/colours/black.jpg",
      imageAlt: "A screen recording being captured by Squint.",
      layout: "normal",
    },
    {
      step: "Standardize",
      title: "Generate Step-by-Step Guides",
      description:
        "Squint instantly transforms raw recordings into clear, editable work instructions and standard operating procedures. No more manual documentation.",
      imageUrl: "https://www.ledr.com/colours/black.jpg",
      imageAlt: "A generated step-by-step guide in the Squint interface.",
      layout: "reversed",
    },
    {
      step: "Organize",
      title: "A Central Hub for Your Know-How",
      description:
        "All captured processes are organized in a secure, searchable knowledge base, creating a single source of truth that replaces outdated paper manuals.",
      imageUrl: "https://www.ledr.com/colours/black.jpg",
      imageAlt: "A searchable knowledge base of work instructions in Squint.",
      layout: "normal",
    },
    {
      step: "Access",
      title: "Instant Answers, On the Job",
      description:
        "Team members get instant visual guidance exactly when and where they need it, dramatically reducing training time and costly errors.",
      imageUrl: "/generated/image-a-manufacturing-worker-standing-on-a-fac.webp",
      imageAlt: "Manufacturing worker accessing visual guidance on tablet on the factory floor.",
      layout: "reversed",
    },
  ];

  // Functions
  /**
   * Handles the click event for the "Learn More" link.
   * Prevents the default anchor tag behavior.
   * @param {MouseEvent} event - The mouse event.
   */
  function handleLearnMoreClick(event: MouseEvent) {
    event.preventDefault();
    // In a real application, this could navigate to a new page or open a modal.
  }
</script>

<section class="bg-white py-24 lg:py-32 {className}">
  <div class="mx-auto w-full max-w-[1728px] px-6 lg:px-8">
    <div class="grid grid-cols-12 gap-4 lg:gap-5">
      <div class="col-span-12 text-center">
        <div class="flex flex-col items-center">
          <div class="flex flex-col items-center gap-4 text-center">
            <h3
              class="font-display text-balance text-4xl font-medium text-gray-900 sm:text-5xl"
            >
              How Squint Turns Process
            </h3>
            <h3
              class="font-display text-balance text-4xl font-medium text-gray-900 sm:text-5xl"
            >
              Into Actionable Knowledge
            </h3>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-16 w-full md:mt-24">
      <div class="grid grid-cols-12 gap-4 lg:gap-5">
        <div class="col-span-12 lg:col-span-10 lg:col-start-2">
          <div class="flex flex-col gap-16 md:gap-24">
            {#each features as feature}
              <article
                class="flex w-full flex-col {feature.layout === 'reversed'
                  ? 'md:flex-row-reverse'
                  : 'md:flex-row'}"
              >
                <div
                  class="relative aspect-square w-full overflow-hidden rounded-t-lg bg-gray-800 md:flex-1 {feature.layout ===
                  'reversed'
                    ? 'md:rounded-r-lg md:rounded-tl-none'
                    : 'md:rounded-l-lg md:rounded-tr-none'}"
                >
                  <img
                    class="inset-0 h-full w-full object-cover"
                    src={feature.imageUrl}
                    alt={feature.imageAlt}
                  />
                </div>
                <div
                  class="flex w-full flex-col items-center justify-center rounded-b-lg bg-gray-900 md:aspect-square md:flex-1 {feature.layout ===
                  'reversed'
                    ? 'md:rounded-l-lg md:rounded-br-none'
                    : 'md:rounded-r-lg md:rounded-bl-none'}"
                >
                  <div class="flex w-full flex-col gap-5 p-8 md:px-24">
                    <span
                      class="font-body text-xl font-normal capitalize text-gray-100"
                      >{feature.step}</span
                    >
                    <div class="flex flex-col gap-5">
                      <h2
                        class="font-display text-balance text-4xl font-medium text-gray-50 lg:text-5xl"
                      >
                        {feature.title}
                      </h2>
                      <p class="font-body max-w-xs text-lg text-gray-300">
                        {feature.description}
                      </p>
                      <a
                        href="#"
                        onclick={handleLearnMoreClick}
                        class="font-body group flex w-max items-center font-medium text-gray-400 transition-colors duration-300 ease-out hover:text-gray-50"
                      >
                        <p class="leading-none">Learn More</p>
                        <svg
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          fill="currentColor"
                          class="ml-1 h-5 w-5 transition-transform duration-300 group-hover:translate-x-1"
                          aria-hidden="true"
                        >
                          <path
                            fill-rule="evenodd"
                            d="M3 10a.75.75 0 01.75-.75h10.638L10.23 5.29a.75.75 0 111.04-1.08l5.5 5.25a.75.75 0 010 1.08l-5.5 5.25a.75.75 0 11-1.04-1.08l4.158-3.96H3.75A.75.75 0 013 10z"
                            clip-rule="evenodd"
                          ></path>
                        </svg>
                      </a>
                    </div>
                  </div>
                </div>
              </article>
            {/each}
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
