<script setup lang="ts">
import { ref } from 'vue'
import { useFixedHeader } from 'vue-use-fixed-header'
const headerRef = ref(null)
const { styles } = useFixedHeader(headerRef)

</script>
<template>
  <header
   ref="headerRef" :style="styles"
    class="fixed Header flex flex-wrap sm:justify-start sm:flex-nowrap z-50 w-full text-sm py-5"
  >
    <nav
      class="max-w-[85rem] w-full mx-auto px-4 flex flex-wrap basis-full items-center justify-between rounded-lg relative p-5 border border-gray-200 bg-white dark:bg-dark dark:border-dark-border "
      aria-label="Global"
    >
      <Logo />

      <div class="sm:order-3 flex items-center">
        <button class="mx-3"><LangSwitcher /></button>
        <button class="mx-3"><ThemeSwitcher /></button>
        <button
          type="button"
          class="sm:hidden hs-collapse-toggle p-2.5 inline-flex justify-center items-center gap-x-2 rounded-lg border border-gray-200 bg-white text-gray-800 shadow-sm hover:bg-gray-50 disabled:opacity-50 disabled:pointer-events-none dark:bg-transparent dark:border-gray-700 dark:text-white dark:hover:bg-white/10 dark:focus:outline-none dark:focus:ring-1 dark:focus:ring-gray-600"
          data-hs-collapse="#navbar-alignment"
          aria-controls="navbar-alignment"
          aria-label="Toggle navigation"
        >
        <div class="hs-collapse-open:hidden flex-shrink-0 w-4 h-4">
          <Icon aria-hidden="true" name="solar:hamburger-menu-linear" class="w-5 h-5 z-10" /> 
        </div>
        <div class="hs-collapse-open:block hidden flex-shrink-0 w-4 h-4">
          <Icon aria-hidden="true" name="solar:home-smile-outline" class="w-5 h-5 z-10" /> 
        </div>
        </button>
      </div>
      <div
        id="navbar-alignment"
        class="hs-collapse hidden overflow-hidden transition-all duration-300 basis-full grow sm:grow-0 sm:basis-auto sm:block sm:order-2"
      >
        <div class="flex flex-col gap-5 mt-5 sm:flex-row sm:items-center sm:mt-0 sm:ps-5">
          <NavLinks />
        </div>
      </div>
    </nav>
  </header>
</template>

<style>
.Header {
  transition: all 0.5s ease-in-out;
}
</style>