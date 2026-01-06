<script setup lang="ts">
// Используем тип NavigationMenuItem для типизации меню
import type { NavigationMenuItem } from "@nuxt/ui";

const items = computed<NavigationMenuItem[]>(() => [
  {
    label: "Головна",
    to: "#",
  },
  {
    label: "Послуги",
    to: "#services",
  },
  {
    label: "Про нас",
    to: "#about",
  },
  {
    label: "Контакти",
    to: "#contacts",
  },
]);
</script>

<template>
  <UHeader
    mode="drawer"
    class="bg-white/80 dark:bg-gray-900/80 backdrop-blur-md border-b border-gray-200 dark:border-gray-800 shadow-sm"
  >
    <template #title>
      <div class="flex items-center gap-2">
        <UIcon name="i-ph-cat" class="w-6 h-6" />
        <span class="font-bold">Грумінг для котиків</span>
      </div>
    </template>

    <UNavigationMenu :items="items" variant="link" />

    <template #right>
      <NuxtLink
        to="tel:+380XXXXXXXXX"
        class="hidden lg:block text-sm font-medium hover:text-primary transition-colors mr-2"
      >
        +38 (0XX) XXX-XX-XX
      </NuxtLink>

      <UColorModeButton />

      <UButton
        label="Записатись"
        variant="solid"
        class="ml-2 rounded-full bg-cameo-400 hover:bg-[#c4a590]"
      />
    </template>

    <template #body>
      <UNavigationMenu :items="items" orientation="vertical" class="-mx-2.5" />
    </template>
  </UHeader>
</template>
