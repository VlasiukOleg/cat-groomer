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
    class="py-8 md:py-24 px-4 md:px-6 bg-[#fafaf9] dark:bg-gray-950 overflow-hidden"
  >
    <UContainer>
      <div class="text-center mb-8 md:mb-16">
        <h2
          class="text-3xl md:text-4xl font-bold text-[#4a4a4a] dark:text-gray-100"
        >
          Давайте Знайомитись
        </h2>
      </div>

      <div class="grid md:grid-cols-2 gap-8 md:gap-16 items-center">
        <div class="hidden md:block relative group order-2 md:order-1">
          <div
            class="absolute -inset-4 bg-primary-100/50 dark:bg-primary-900/10 rounded-[2.5rem] blur-2xl transition-all duration-500 group-hover:blur-3xl"
          ></div>
          <div
            class="relative h-[600px] rounded-[2rem] overflow-hidden shadow-xl transition-transform duration-500 hover:scale-[1.02] border-4 border-white dark:border-gray-800"
          >
            <img
              src="/images/rimma-groomer.jpg"
              alt="Рімма - професійний грумер"
              class="w-full h-full object-cover"
            />
          </div>
        </div>

        <div class="space-y-6 md:space-y-8 order-1 md:order-2">
          <div
            class="flex flex-col items-center md:items-start text-center md:text-left space-y-6"
          >
            <p
              class="text-xl md:text-2xl text-[#4a4a4a] dark:text-gray-100 font-medium"
            >
              Мене звати
              <span class="text-cameo-400 dark:text-primary-400 font-bold"
                >Рімма</span
              >, я професійний кото-грумер.
            </p>

            <div class="md:hidden relative">
              <div
                class="absolute -inset-2 bg-cameo-200/50 rounded-full blur-xl"
              ></div>
              <div
                class="relative w-48 h-48 rounded-full overflow-hidden border-4 border-white shadow-lg"
              >
                <img
                  src="/images/rimma-groomer.jpg"
                  alt="Рімма Грумер"
                  class="w-full h-full object-cover"
                />
              </div>
            </div>

            <p
              class="text-base md:text-lg text-[#7a7a7a] dark:text-gray-400 leading-relaxed"
            >
              Я спеціалізуюся саме на котах і працюю з урахуванням їх характеру,
              віку та рівня адаптації до процедур.
            </p>

            <p
              class="text-base md:text-lg text-[#7a7a7a] dark:text-gray-400 leading-relaxed"
            >
              Моя мета — не просто красива шерсть, а спокійний кіт і здоровий
              догляд, який не шкодить психіці тварини.
            </p>
          </div>

          <div class="pt-2">
            <p class="text-lg text-[#4a4a4a] dark:text-gray-200 font-bold mb-4">
              Я допомагаю:
            </p>
            <ul class="space-y-3 md:space-y-4">
              <li
                v-for="(item, index) in helpItems"
                :key="index"
                class="flex items-center gap-3 group/item transition-transform duration-300 hover:translate-x-2"
              >
                <div class="mt-2 shrink-0">
                  <UIcon name="i-ph-cat" class="w-6 h-6 text-cameo-400" />
                </div>
                <p
                  class="text-base md:text-lg text-[#7a7a7a] dark:text-gray-400 text-left"
                >
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
                просто потрібен правильний підхід 💙"
              </p>
            </div>
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>
