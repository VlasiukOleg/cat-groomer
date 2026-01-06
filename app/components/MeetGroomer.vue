<script setup lang="ts">
const helpItems = [
  "котикам, які бояться грумінгу",
  "котам із ковтунами та чутливою шкірою",
  "власникам, які хочуть гуманний та усвідомлений догляд",
];
</script>

<template>
  <section
    id="meet"
    class="py-16 md:py-24 px-4 md:px-6 bg-[#fafaf9] dark:bg-gray-950 overflow-hidden"
  >
    <UContainer>
      <div class="text-center mb-12 md:mb-16">
        <h2
          class="text-3xl md:text-4xl font-bold text-[#4a4a4a] dark:text-gray-100"
        >
          Давайте Знайомитись
        </h2>
      </div>

      <div class="grid md:grid-cols-2 gap-8 md:gap-16 items-center">
        <div class="relative group order-2 md:order-1">
          <div
            class="absolute -inset-4 bg-primary-100/50 dark:bg-primary-900/10 rounded-[2.5rem] blur-2xl transition-all duration-500 group-hover:blur-3xl"
          ></div>

          <div
            class="relative h-[400px] md:h-[600px] rounded-[2rem] overflow-hidden shadow-xl transition-transform duration-500 hover:scale-[1.02]"
          >
            <img
              src="https://images.unsplash.com/photo-1725419876939-f8f9987cf0d2?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=1080"
              alt="Рімма - професійний грумер"
              class="w-full h-full object-cover"
            />
          </div>
        </div>

        <div class="space-y-6 md:space-y-8 order-1 md:order-2">
          <div class="space-y-4">
            <p
              class="text-xl md:text-2xl text-[#4a4a4a] dark:text-gray-100 font-medium"
            >
              Мене звати
              <span class="text-cameo-400 dark:text-primary-400 font-bold"
                >Рімма</span
              >, я професійний кото-грумер.
            </p>

            <p
              class="text-lg text-[#7a7a7a] dark:text-gray-400 leading-relaxed"
            >
              Я спеціалізуюся саме на котах і працюю з урахуванням їх характеру,
              віку та рівня адаптації до процедур.
            </p>

            <p
              class="text-lg text-[#7a7a7a] dark:text-gray-400 leading-relaxed"
            >
              Моя мета — не просто красива шерсть, а спокійний кіт і здоровий
              догляд, який не шкодить психіці тварини.
            </p>
          </div>

          <div class="pt-2">
            <p class="text-lg text-[#4a4a4a] dark:text-gray-200 font-bold mb-4">
              Я допомагаю:
            </p>
            <ul class="space-y-4">
              <li
                v-for="(item, index) in helpItems"
                :key="index"
                class="flex items-start gap-3 group/item transition-transform duration-300 hover:translate-x-2"
              >
                <div class="mt-2">
                  <UIcon name="i-ph-cat" class="w-5 h-5 text-cameo-400" />
                </div>
                <p class="text-lg text-[#7a7a7a] dark:text-gray-400">
                  {{ item }}
                </p>
              </li>
            </ul>
          </div>

          <div class="pt-4">
            <div
              class="px-6 py-5 bg-[#f8f6f4] dark:bg-gray-900 border-l-4 border-cameo-400 rounded-r-2xl rounded-l-sm shadow-sm"
            >
              <p
                class="text-lg text-[#4a4a4a] dark:text-gray-200 italic leading-relaxed"
              >
                "Ваш кіт — не <span class="font-bold">складний</span>, йому
                просто потрібен правильный підхід"
              </p>
            </div>
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>
