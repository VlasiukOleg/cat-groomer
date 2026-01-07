<script setup lang="ts">
// Масив послуг
const servicesList = [
  {
    icon: "i-ph-drop",
    title: "Купання і вичісування",
    price: "1700 грн",
    duration: "2 години",
    items: [
      "Стрижка кігтів — акуратно та безпечно",
      "Чистка вушок — делікатно, без травмування",
      "Професійне вичісування — видалення підшерстя та ковтунів",
      "Купання професійними шампунями — з урахуванням типу шерсті та стану шкіри",
      "Нанесення кондиціонера / доглядової маски — для зволоження, блиску та легкого розчісування",
      "Сушіння шерсті - під бустер — рівномірне та швидке, або в спеціальному боксі, якщо котик боїться гучних звуків чи фену",
    ],
    defaultOpen: true,
  },
  {
    icon: "i-ph-broom",
    title: "Вичісування",
    price: "1050 грн",
    duration: "1 год",
    items: [
      "Стрижка кігтів — акуратно та безпечно",
      "Чистка вушок — делікатно, без травмування",
      "Професійне вичісування — видалення підшерстя та початкових ковтунів з урахуванням типу шерсті",
    ],
    defaultOpen: false,
  },
  {
    icon: "i-ph-heart",
    title: "Візит знайомство, адаптація до грумінгу",
    price: "900 грн",
    duration: "45 хв",
    description:
      "Адаптація до грумінгу — це м’яке та поступове знайомство котика з простором та процедурами догляду без стресу, примусу та перевантаження. Послуга спрямована на формування спокійного ставлення до грумінгу та довіри до процесу.",
    important: [
      "процедура не має на меті виконання всього комплексу за один візит",
      "обсяг процедур визначається індивідуально, залежно від стану та поведінки котика",
      "для стійкого результату може знадобитися кілька сеансів адаптації",
    ],
    items: [
      "знайомство котика з простором та грумером",
      "поступове привчання до дотиків і інструментів",
      "адаптація до звуків (без використання гучного обладнання)",
      "легке вичісування — за готовністю котика",
      "стрижка кігтів — за згоди тварини",
      "делікатний огляд та, за потреби, легка чистка вушок",
      "паузи або завершення процедури при ознаках стресу",
    ],
    defaultOpen: false,
  },
  {
    icon: "i-ph-scissors",
    title: "Манікюр",
    price: "350 грн",
    duration: "20 хв",
    items: [
      "акуратна стрижка кігтів",
      "мінімальна обробка без стресу",
      "індивідуальний підхід",
    ],
    defaultOpen: false,
  },
];

const accordionStates = ref<Record<number, string[]>>(
  Object.fromEntries(servicesList.map((_, i) => [i, i === 0 ? ["0"] : []]))
);

const scrollToContact = () => {
  document.getElementById("contacts")?.scrollIntoView({ behavior: "smooth" });
};
</script>

<template>
  <section id="services" class="py-16 md:py-24 bg-white dark:bg-gray-950">
    <UContainer>
      <div class="text-center mb-12">
        <h2
          class="text-3xl md:text-4xl font-bold text-[#4a4a4a] dark:text-gray-100"
        >
          Наші Послуги
        </h2>
      </div>

      <div class="max-w-4xl mx-auto space-y-4 md:space-y-6">
        <div
          v-for="(service, index) in servicesList"
          :key="index"
          class="bg-[#fafaf9] dark:bg-gray-900 rounded-2xl md:rounded-3xl border border-[#e8e4e0] dark:border-gray-800 overflow-hidden shadow-sm"
        >
          <div
            class="bg-linear-to-r from-[#4279ce] to-[#cee3f6] px-4 py-3 md:px-6 md:py-4"
          >
            <div class="flex items-center gap-3 md:gap-4">
              <div
                class="w-10 h-10 md:w-12 md:h-12 rounded-xl bg-white/20 backdrop-blur-md flex items-center justify-center shrink-0"
              >
                <UIcon
                  :name="service.icon"
                  class="w-6 h-6 md:w-7 md:h-7 text-white"
                />
              </div>
              <h3
                class="text-white text-base md:text-xl font-bold leading-tight italic"
              >
                {{ service.title }}
              </h3>
            </div>
          </div>

          <div class="p-4 md:p-6">
            <div class="md:hidden">
              <UAccordion
                v-model="accordionStates[index]"
                :items="[{ label: 'Що входить до послуги', slot: 'content' }]"
                :ui="{
                  trigger:
                    'text-[#7a7a7a] font-bold px-0 hover:no-underline focus:ring-0',
                  trailingIcon: 'w-5 h-5 text-cameo-500',
                }"
              >
                <template #content>
                  <div class="space-y-4 pt-2">
                    <p
                      v-if="service.description"
                      class="text-xs text-[#4a4a4a] leading-relaxed bg-[#f0ebe7] p-3 rounded-xl italic border-l-2 border-cameo-400"
                    >
                      {{ service.description }}
                    </p>

                    <ul class="space-y-2">
                      <li
                        v-for="point in service.items"
                        :key="point"
                        class="flex gap-2 text-xs text-[#7a7a7a]"
                      >
                        <div
                          class="w-1.5 h-1.5 rounded-full bg-cameo-400 mt-1.5 shrink-0"
                        />
                        <span class="leading-relaxed">{{ point }}</span>
                      </li>
                    </ul>

                    <div
                      v-if="service.important"
                      class="bg-amber-50 dark:bg-amber-950/20 p-3 rounded-xl border border-amber-100 dark:border-amber-900/30"
                    >
                      <p
                        class="text-[11px] font-bold text-amber-800 dark:text-amber-400 mb-1 flex items-center gap-1"
                      >
                        <UIcon name="i-ph-warning-circle-bold" /> Важливо:
                      </p>
                      <ul class="space-y-1">
                        <li
                          v-for="imp in service.important"
                          :key="imp"
                          class="text-[10px] text-amber-700/80 dark:text-amber-500/80 leading-tight"
                        >
                          • {{ imp }}
                        </li>
                      </ul>
                    </div>

                    <div
                      class="flex justify-between items-center pt-4 border-t border-dashed border-gray-300"
                    >
                      <span
                        class="font-bold text-[#4a4a4a] flex items-center gap-1"
                      >
                        <UIcon name="i-ph-banknote" class="text-cameo-500" />
                        {{ service.price }}
                      </span>
                      <span
                        class="text-xs text-[#7a7a7a] flex items-center gap-1"
                      >
                        <UIcon name="i-ph-clock" class="text-cameo-500" />
                        {{ service.duration }}
                      </span>
                    </div>
                  </div>
                </template>
              </UAccordion>
            </div>

            <div class="hidden md:block">
              <p
                v-if="service.description"
                class="mb-6 text-sm text-[#4a4a4a] leading-relaxed bg-[#f0ebe7] p-4 rounded-2xl italic border-l-4 border-cameo-400"
              >
                {{ service.description }}
              </p>

              <div class="flex justify-between items-start gap-8">
                <div class="flex-grow space-y-6">
                  <ul class="grid grid-cols-2 gap-x-8 gap-y-3">
                    <li
                      v-for="point in service.items"
                      :key="point"
                      class="flex gap-2 text-sm text-[#7a7a7a]"
                    >
                      <div
                        class="w-1.5 h-1.5 rounded-full bg-cameo-400 mt-2 shrink-0"
                      />
                      <span class="leading-relaxed">{{ point }}</span>
                    </li>
                  </ul>

                  <div
                    v-if="service.important"
                    class="bg-amber-50 dark:bg-amber-900/10 p-4 rounded-2xl border border-amber-100 dark:border-amber-900/20"
                  >
                    <p
                      class="text-xs font-bold text-amber-800 dark:text-amber-400 mb-2 flex items-center gap-2"
                    >
                      <UIcon name="i-ph-warning-circle-bold" class="w-4 h-4" />
                      Важливо:
                    </p>
                    <ul class="space-y-1">
                      <li
                        v-for="imp in service.important"
                        :key="imp"
                        class="text-xs text-amber-700/80 dark:text-amber-500/70"
                      >
                        • {{ imp }}
                      </li>
                    </ul>
                  </div>
                </div>

                <div
                  class="shrink-0 flex flex-col items-end gap-2 border-l border-[#e8e4e0] pl-8"
                >
                  <div
                    class="flex items-center gap-2 text-xl font-bold text-[#4a4a4a]"
                  >
                    <UIcon name="i-ph-banknote" class="text-cameo-500" />
                    {{ service.price }}
                  </div>
                  <div class="flex items-center gap-2 text-sm text-[#7a7a7a]">
                    <UIcon name="i-ph-clock" class="text-cameo-500" />
                    {{ service.duration }}
                  </div>
                  <UButton
                    label="Записатися"
                    color="neutral"
                    class="mt-4 px-6 font-bold"
                    @click="scrollToContact"
                    variant="outline"
                  />
                </div>
              </div>
            </div>

            <div class="md:hidden mt-4">
              <UButton
                block
                label="Записатися"
                variant="outline"
                color="neutral"
                class="py-3 font-bold"
                @click="scrollToContact"
              />
            </div>
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>
