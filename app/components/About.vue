<script setup lang="ts">
const features = [
  {
    title: "Сертифіковані Професіонали",
    description:
      "Усі грумери навчені спеціально для роботи з поведінкою та доглядом за котами",
  },
  {
    title: "Досвід Без Стресу",
    description:
      "Ми використовуємо заспокійливі техніки та працюємо в темпі вашого кота",
  },
  {
    title: "Преміум Продукти",
    description: "Тільки найкращі, безпечні для котів засоби для грумінгу",
  },
];
</script>

<template>
  <section
    id="about"
    class="py-8 md:py-24 bg-[#f8f6f4] dark:bg-gray-900 overflow-hidden"
  >
    <UContainer>
      <div class="grid md:grid-cols-2 gap-12 md:gap-16 items-center">
        <div class="relative group order-2 md:order-1">
          <div
            class="absolute -inset-4 bg-primary-200/30 dark:bg-primary-900/20 rounded-[2.5rem] blur-2xl group-hover:blur-3xl transition-all duration-500"
          ></div>

          <div
            class="relative h-[350px] md:h-[500px] rounded-[2rem] overflow-hidden shadow-2xl transition-transform duration-500 hover:scale-[1.02]"
          >
            <img
              src="https://images.unsplash.com/photo-1715828545824-feccd961b1ee?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=1080"
              alt="Професійний грумінг котів"
              class="w-full h-full object-cover"
            />
          </div>
        </div>

        <div class="space-y-6 md:space-y-8 order-1 md:order-2">
          <div class="space-y-4">
            <h2
              class="text-3xl md:text-5xl font-bold text-[#4a4a4a] dark:text-gray-100 leading-tight"
            >
              Чому Обирають Нас
            </h2>
            <p
              class="text-lg text-[#7a7a7a] dark:text-gray-400 leading-relaxed"
            >
              Ми розуміємо, що коти — унікальні створіння з особливими
              потребами. Наші сертифіковані грумери спеціалізуються на догляді
              за котами, використовуючи ніжні техніки та створюючи спокійне
              середовище без стресу.
            </p>
          </div>

          <ul class="space-y-6">
            <li
              v-for="(feature, index) in features"
              :key="feature.title"
              class="flex items-start gap-4 group/item"
            >
              <div class="flex-shrink-0 mt-1.5">
                <div
                  class="w-3 h-3 rounded-full bg-primary shadow-[0_0_10px_rgba(212,181,160,0.8)] group-hover/item:scale-150 transition-transform duration-300"
                ></div>
              </div>

              <div
                class="transition-transform duration-300 group-hover/item:translate-x-2"
              >
                <p class="text-[#4a4a4a] dark:text-gray-200">
                  <span class="font-bold text-lg block md:inline">{{
                    feature.title
                  }}</span>
                  <span class="md:mx-1">—</span>
                  <span class="text-[#7a7a7a] dark:text-gray-400">{{
                    feature.description
                  }}</span>
                </p>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </UContainer>
  </section>
</template>
