<template>
  <div class="relative z-10 pb-8 bg-white lg:max-w-2xl lg:w-full">
    <div>
      <div class="relative pt-6 px-4 sm:px-6 lg:px-8">
        <nav
          class="
            relative
            flex
            items-center
            justify-between
            sm:h-10
            lg:justify-start
          "
          aria-label="Global"
        >
          <div class="flex items-center flex-grow flex-shrink-0 lg:flex-grow-0">
            <div class="flex items-center justify-between w-full md:w-auto">
              <NuxtLink to="/">
                <span class="sr-only">Workflow</span>
                <img class="h-8 w-auto sm:h-10" src="/colored-logo.svg" />
              </NuxtLink>
              <div class="-mr-2 flex items-center md:hidden">
                <button
                  type="button"
                  class="
                    bg-white
                    rounded-md
                    p-2
                    inline-flex
                    items-center
                    justify-center
                    text-gray-400
                    hover:text-gray-500 hover:bg-gray-100
                    focus:outline-none
                    focus:ring-2
                    focus:ring-inset
                    focus:ring-green-500
                  "
                  aria-expanded="false"
                >
                  <span class="sr-only">Open main menu</span>
                  <!-- Heroicon name: outline/menu -->
                  <svg
                    class="h-6 w-6"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    viewBox="0 0 24 24"
                    stroke="currentColor"
                    aria-hidden="true"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M4 6h16M4 12h16M4 18h16"
                    />
                  </svg>
                </button>
              </div>
            </div>
          </div>
          <div class="hidden md:block md:ml-10 md:pr-4 md:space-x-8">
            <NuxtLink to="/blog">
              <span class="font-medium text-gray-500 hover:text-gray-900"
                >Blog</span
              >
            </NuxtLink>

            <a href="#" class="font-medium text-green-600 hover:text-green-500"
              >Log in</a
            >
          </div>
        </nav>
      </div>

      <!--
            Mobile menu, show/hide based on menu open state.

            Entering: "duration-150 ease-out"
              From: "opacity-0 scale-95"
              To: "opacity-100 scale-100"
            Leaving: "duration-100 ease-in"
              From: "opacity-100 scale-100"
              To: "opacity-0 scale-95"
          -->
      <div
        class="
          absolute
          z-10
          top-0
          inset-x-0
          p-2
          transition
          transform
          origin-top-right
          hidden
        "
      >
        <div
          class="
            rounded-lg
            shadow-md
            bg-white
            ring-1 ring-black ring-opacity-5
            overflow-hidden
          "
        >
          <div class="px-5 pt-4 flex items-center justify-between">
            <div>
              <img class="h-8 w-auto" src="/colored-logo.svg" alt="" />
            </div>
            <div class="-mr-2">
              <button
                type="button"
                class="
                  bg-white
                  rounded-md
                  p-2
                  inline-flex
                  items-center
                  justify-center
                  text-gray-400
                  hover:text-gray-500 hover:bg-gray-100
                  focus:outline-none
                  focus:ring-2
                  focus:ring-inset
                  focus:ring-green-500
                "
              >
                <span class="sr-only">Close main menu</span>
                <!-- Heroicon name: outline/x -->
                <svg
                  class="h-6 w-6"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M6 18L18 6M6 6l12 12"
                  />
                </svg>
              </button>
            </div>
          </div>
          <div class="px-2 pt-2 pb-3 space-y-1">
            <a
              href="#"
              class="
                block
                px-3
                py-2
                rounded-md
                text-base
                font-medium
                text-gray-700
                hover:text-gray-900 hover:bg-gray-50
              "
              >Blog</a
            >
          </div>
          <a
            href="#"
            class="
              block
              w-full
              px-5
              py-3
              text-center
              font-medium
              text-green-600
              bg-gray-50
              hover:bg-gray-100
            "
          >
            Log in
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
