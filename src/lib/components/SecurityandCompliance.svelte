<script lang="ts">
  // Props
  let { className = "" }: { className?: string } = $props();

  // No internal state is needed for this static component.
</script>

<section class="bg-[var(--color-background)] py-24 lg:py-32 {className}">
  <div class="mx-auto max-w-7xl border-t border-neutral-800 px-6 lg:px-8">
    <div class="flex flex-col gap-16 lg:gap-20">
      <div
        class="flex flex-col gap-5 pt-16 lg:flex-row lg:items-start lg:gap-10 lg:pt-20"
      >
        <div class="w-full lg:w-1/4">
          <div class="flex items-center gap-3">
            <span class="bg-primary-500 h-2.5 w-2.5 rounded-full"></span>
            <p class="font-body text-sm text-neutral-950">
              Security & Compliance
            </p>
          </div>
        </div>
        <div
          class="flex flex-1 flex-col items-start gap-10 lg:flex-row lg:items-end lg:justify-between"
        >
          <h2
            class="font-display text-4xl font-normal leading-tight tracking-tighter text-neutral-950 md:text-5xl lg:text-6xl"
          >
            Your Processes are Your IP.
            <br />
            <span class="text-neutral-950/60">We Keep Them Secure.</span>
          </h2>
          <a
            href="#"
            class="shrink-0 rounded-full bg-neutral-50 px-5 py-3 text-base font-medium text-neutral-900 transition-colors hover:bg-neutral-200"
          >
            Learn About Security
          </a>
        </div>
      </div>
      <div class="flex">
        <div class="hidden w-1/4 shrink-0 lg:block"></div>
        <div
          class="grid flex-1 grid-cols-1 gap-1.5 sm:grid-cols-2 lg:grid-cols-4"
        >
          <div
            class="flex aspect-[4/5] flex-col justify-between rounded-2xl bg-neutral-200 p-5"
          >
            <div>
              <div class="h-12 w-12 text-neutral-900">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M9 12.75L11.25 15 15 9.75m-3-7.036A11.959 11.959 0 013.598 6 11.99 11.99 0 003 9.749c0 5.592 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.602-3.751m-14.254-2.48a11.959 11.959 0 0114.254 0M12 15.75a3 3 0 01-3-3m3 3a3 3 0 003-3m-3 3v3.75"
                  ></path>
                </svg>
              </div>
              <h3
                class="font-display mt-16 text-xl leading-tight text-neutral-900"
              >
                Enterprise Security
              </h3>
            </div>
            <p class="font-body text-sm leading-tight text-neutral-700">
              Your process data is protected with end-to-end encryption and
              hosted in secure, SOC 2 Type II certified environments.
            </p>
          </div>
          <div
            class="flex aspect-[4/5] flex-col justify-between rounded-2xl bg-neutral-200 p-5"
          >
            <div>
              <div class="h-12 w-12 text-neutral-900">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M2.036 12.322a1.012 1.012 0 010-.639l3.423-7.507a1.012 1.012 0 01.963-.69h11.154c.473 0 .898.244 1.087.638l3.423 7.507a1.012 1.012 0 010 .639l-3.423 7.507a1.012 1.012 0 01-.963.69h-11.154a1.012 1.012 0 01-.963-.69L2.036 12.322z"
                  ></path>
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"
                  ></path>
                </svg>
              </div>
              <h3
                class="font-display mt-16 text-xl leading-tight text-neutral-900"
              >
                Data Privacy by Design
              </h3>
            </div>
            <p class="font-body text-sm leading-tight text-neutral-700">
              We process your data to create guides, but we never use it for
              training our models. Your knowledge remains yours alone.
            </p>
          </div>
          <div
            class="flex aspect-[4/5] flex-col justify-between rounded-2xl bg-neutral-200 p-5"
          >
            <div>
              <div class="h-12 w-12 text-neutral-900">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M21.75 9v.906a2.25 2.25 0 01-1.183 1.981l-6.478 3.488M2.25 9v.906a2.25 2.25 0 001.183 1.981l6.478 3.488m8.839 2.51-4.66-2.51m0 0l-1.023-.55a2.25 2.25 0 00-2.134 0l-1.022.55m0 0l-4.661 2.51m16.5 1.615a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V8.844a2.25 2.25 0 011.183-1.981l7.5-4.039a2.25 2.25 0 012.134 0l7.5 4.039a2.25 2.25 0 011.183 1.98V19.5z"
                  ></path>
                </svg>
              </div>
              <h3
                class="font-display mt-16 text-xl leading-tight text-neutral-900"
              >
                No Training on your Data
              </h3>
            </div>
            <p class="font-body text-sm leading-tight text-neutral-700">
              You have full control and ownership of your data. Squint is fully
              compliant with data privacy regulations.
            </p>
          </div>
          <div
            class="flex aspect-[4/5] flex-col justify-between rounded-2xl bg-neutral-200 p-5"
          >
            <div>
              <div class="h-12 w-12 text-neutral-900">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    d="M15.75 6a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0zM4.501 20.118a7.5 7.5 0 0114.998 0A17.933 17.933 0 0112 21.75c-2.676 0-5.216-.584-7.499-1.632z"
                  ></path>
                </svg>
              </div>
              <h3
                class="font-display mt-16 text-xl leading-tight text-neutral-900"
              >
                Access Control
              </h3>
            </div>
            <p class="font-body text-sm leading-tight text-neutral-700">
              Granular user roles and permissions ensure that only authorized personnel can view, edit, or create sensitive manufacturing process documentation.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
