<script setup lang="ts">
import type { NavigationMenuItem } from "@nuxt/ui";

const items: NavigationMenuItem[] = [
  {
    label: "Політика конфіденційності",
    to: "https://go.nuxt.com/figma-ui",
    target: "_blank",
  },
];
</script>

<template>
  <UFooter :ui="{ 
    root: 'border-t border-gray-200 dark:border-gray-800', 
    bottom: 'sm: py-4' 
  }">
    <template #left>
      <p class="text-muted text-sm">
        Copyright © {{ new Date().getFullYear() }}
      </p>
    </template>

    <UNavigationMenu :items="items" variant="link" />
  </UFooter>
</template>
