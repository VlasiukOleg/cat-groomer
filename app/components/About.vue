<script setup lang="ts">
const features = [
  {
    title: "Сертифікований кото-грумер",
    description:
      "Я маю професійну сертифікацію та спеціалізоване навчання з грумінгу котів і роботи з їхньою поведінкою.",
  },
  {
    title: "Адаптація та привчання до процедур",
    description:
      "Я допомагаю котикам поступово звикнути до грумінгу — особливо тим, хто боїться або має негативний досвід. Процес адаптації відбувається м’яко та без примусу.",
  },
  {
    title: "Контроль емоційного стану",
    description:
      "Під час кожної процедури я постійно стежу за емоційним і фізичним станом котика та коригую хід роботи за потреби.",
  },
  {
    title: "Професійна косметика",
    description:
      "Використовую якісну професійну косметику для котів, яку підбираю індивідуально — відповідно до типу шерсті та стану шкіри.",
  },
  {
    title: "Гуманний підхід",
    description:
      "Жодних фізичних методів впливу, силової фіксації чи стресових технік. У роботі застосовується виключно гуманний підхід з повагою до меж тварини.",
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
              src="/images/about.jpg"
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
              Чому обирають мене як кото-грумера
            </h2>
            <p
              class="text-base md:text-lg text-[#7a7a7a] dark:text-gray-400 leading-relaxed"
            >
              Я працюю виключно з котами та розумію, що якісний грумінг — це не
              швидкість, а безпека, адаптація та контроль емоційного стану
              тварини.
            </p>
          </div>

          <ul class="space-y-6">
            <li
              v-for="(feature, index) in features"
              :key="feature.title"
              class="flex items-start gap-4 group/item"
            >
              <div class="shrink-0 mt-1.5">
                <div
                  class="w-3 h-3 rounded-full bg-cameo-400 shadow-[0_0_10px_rgba(212,181,160,0.8)] group-hover/item:scale-150 transition-transform duration-300"
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
      <AboutNoShaveAccordion />
    </UContainer>
  </section>
</template>
