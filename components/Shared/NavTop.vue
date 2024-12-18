<template>
  <header class="flex justify-center w-full py-2 px-4 lg:py-5 lg:px-6 bg-primary-700 border-b border-neutral-200">
    <div
      class="flex flex-wrap justify-between lg:flex-nowrap items-center flex-row md:justify-start h-full max-w-[1536px] w-full">
      <SfButton variant="tertiary" square class="md:hidden text-white" aria-label="Go back">
        <SfIconArrowBack />
      </SfButton>
      <div class="flex items-center">
        <a href="#" id="main-logo" aria-label="SF Homepage"
          class="inline-block mr-4 focus-visible:outline focus-visible:outline-offset focus-visible:rounded-sm shrink-0">
          <img src="https://storage.googleapis.com/sfui_docs_artifacts_bucket_public/production/vsf_logo_white.svg"
            alt="Sf Logo" class="w-[175px] md:h-6 md:w-[176px] lg:w-[12.5rem] lg:h-[1.75rem]" />
        </a>
        <SfButton variant="tertiary" square class="md:hidden text-white" aria-label="Search">
          <SfIconSearch />
        </SfButton>
      </div>

      <nav class="hidden md:flex flex-1 justify-end lg:order-last lg:ml-4">
        <div class="flex flex-row flex-nowrap">
          <SfButton v-for="actionItem in actionItems" :key="actionItem.ariaLabel"
            class="text-white hover:text-white active:text-white hover:bg-primary-800 active:bg-primary-900 mr-2 -ml-0.5 rounded-md"
            :aria-label="actionItem.ariaLabel" variant="tertiary" square>
            <template #prefix>
              <Component :is="actionItem.icon" />
            </template>
            <span v-if="actionItem.role === 'login'" class="hidden xl:inline-flex whitespace-nowrap">{{
              actionItem.label
              }}</span>
          </SfButton>
        </div>
      </nav>
    </div>
  </header>
</template>
<script lang="ts" setup>
import { ref } from 'vue';
import {
  SfButton,
  SfIconShoppingCart,
  SfIconFavorite,
  SfIconPerson,
  SfIconExpandMore,
  SfInput,
  SfIconSearch,
  SfIconMenu,
  SfIconArrowBack,
} from '@storefront-ui/vue';

const actionItems = [
  {
    icon: SfIconShoppingCart,
    ariaLabel: 'Cart',
    role: 'button',
    label: '',
  },
  {
    icon: SfIconFavorite,
    ariaLabel: 'Wishlist',
    role: 'button',
    label: '',
  },
  {
    label: 'Log in',
    icon: SfIconPerson,
    ariaLabel: 'Log in',
    role: 'login',
  },
];


</script>
