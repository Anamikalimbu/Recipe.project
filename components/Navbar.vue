<template>
    <header class=" bg-yellow-950 flex justify-center w-full py-2 px-4 lg:py-5 lg:px-6  border-b border-neutral-200">
      <div class="flex flex-wrap lg:flex-nowrap items-center flex-row justify-start h-full max-w-[1536px] w-full">
        <a
          href="#"
          aria-label="SF Homepage"
          class="inline-block mr-4 focus-visible:outline focus-visible:outline-offset focus-visible:rounded-sm shrink-0"
        >
          <picture>
            <source srcset=""  />
            <img
              src="~assets/images/logo.png"
              alt="Sf Logo"
              class=" w-50 h-20 "
          />

          </picture>
        </a>
        <form
          role="search"
          class="flex flex-[100%] order-last lg:order-3 mt-2 lg:mt-0 pb-2 lg:pb-0 "
          @submit.prevent="search"
        >
          <SfInput
            v-model="inputValue"
            type="search"
            class="[&::-webkit-search-cancel-button]:appearance-none"
            placeholder="Search"
            wrapper-class="flex-1 h-10 pr-0"
            size="base"
          >
            <template #suffix>
              <span class="flex items-center">
                <SfButton
                  variant="tertiary"
                  square
                  aria-label="search"
                  type="submit"
                  class="rounded-l-none hover:bg-transparent active:bg-transparent"
                >
                  <SfIconSearch />
                </SfButton>
              </span>
            </template>
          </SfInput>
        </form>

        <nav class="flex-1 flex justify-end lg:order-last lg:ml-4">
          <div class="flex flex-row flex-nowrap">
            <SfButton
              v-for="actionItem in actionItems"
              :key="actionItem.ariaLabel"
              class="mr-2 -ml-0.5 rounded-md text-primary-700 hover:bg-primary-100 active:bg-primary-200 hover:text-primary-600 active:text-primary-700"
              :aria-label="actionItem.ariaLabel"
              variant="tertiary"
              square
            >
            </SfButton>
          </div>
        </nav>
        <NuxtLink class=" me-3 text-white hover:text-red-600" to="/">Home</NuxtLink>
        <NuxtLink class=" me-3 text-white hover:text-red-600" to="/about">About</NuxtLink>
        <NuxtLink class=" me-3 text-white hover:text-red-600" to="/contact">Contact </NuxtLink>
        <NuxtLink class=" me-3 text-white hover:text-red-600" to="/products">Product</NuxtLink>
        <NuxtLink class=" me-3 text-white hover:text-red-600" to="/products/byalphabet">Alphabet</NuxtLink>


      </div>
    </header>
  </template>
  <script setup>
  import { ref } from 'vue';
  import {
    SfButton,
    SfIconPerson,
    SfIconExpandMore,
    SfInput,
    SfIconSearch,
    SfIconMenu,
  } from '@storefront-ui/vue';
  
  const actionItems = [
    {
      label: 'Log in',
      icon: SfIconPerson,
      ariaLabel: 'Log in',
      role: 'login',
    },
  ];
  
  const inputValue = ref('');
  
  const search = () => {
    alert(`Successfully found 10 results for ${inputValue.value}`);

  };
  </script>
  <style scoped>
  </style>
  