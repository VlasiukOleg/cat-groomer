<script setup lang="ts">
const services = [
  {
    icon: "i-heroicons-scissors",
    title: "Стрижка Шерсті",
    description:
      "Ніжна стрижка та стайлінг, щоб ваш кіт виглядав чудово, зберігаючи комфорт.",
  },
  {
    icon: "i-heroicons-beaker", // Можно заменить на любую иконку капли
    title: "Купання та Шампунь",
    description:
      "Розкішні ванни з використанням м'яких, безпечних для котів засобів, які роблять шерсть м'якою та блискучою.",
  },
  {
    icon: "i-heroicons-sparkles",
    title: "Догляд за Кігтями",
    description:
      "Професійне підстригання кігтів та догляд за подушечками лап для здоров'я та комфорту вашого кота.",
  },
  {
    icon: "i-heroicons-heart",
    title: "Спеціальний Догляд",
    description:
      "Індивідуальні плани грумінгу для літніх котів, тривожних вихованців або особливих потреб.",
  },
];
</script>

<template>
  <section id="services" class="py-16 md:py-24 bg-white dark:bg-gray-950">
    <UContainer>
      <div class="text-center mb-12 md:mb-16 space-y-4">
        <h2
          class="text-3xl md:text-4xl font-bold text-[#4a4a4a] dark:text-gray-100"
        >
          Наші Послуги
        </h2>
        <p
          class="text-lg md:text-xl text-[#7a7a7a] dark:text-gray-400 max-w-2xl mx-auto"
        >
          Комплексні рішення з грумінгу, адаптовані до унікальних потреб вашого
          кота
        </p>
      </div>

      <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6 md:gap-8">
        <div
          v-for="(service, index) in services"
          :key="service.title"
          class="group p-6 md:p-8 rounded-3xl bg-[#f8f6f4] dark:bg-gray-900 hover:bg-[#f0ebe7] dark:hover:bg-gray-800 transition-all duration-300 transform hover:-translate-y-2 hover:shadow-xl shadow-cameo-200/50"
        >
          <div
            class="w-12 h-12 md:w-14 md:h-14 rounded-full bg-[#e8d7c8] dark:bg-gray-700 flex items-center justify-center mb-6 group-hover:rotate-[360deg] transition-transform duration-700"
          >
            <UIcon
              :name="service.icon"
              class="w-6 h-6 md:w-7 md:h-7 text-[#8b6f5c] dark:text-cameo-300"
            />
          </div>

          <h3
            class="text-lg md:text-xl font-bold text-[#4a4a4a] dark:text-gray-100 mb-3"
          >
            {{ service.title }}
          </h3>
          <p class="text-[#7a7a7a] dark:text-gray-400 leading-relaxed">
            {{ service.description }}
          </p>
        </div>
      </div>
    </UContainer>
  </section>
</template>
