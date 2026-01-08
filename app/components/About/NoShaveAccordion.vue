<script setup lang="ts">
const isOpen = ref(false);
</script>

<template>
  <div class="max-w-4xl mx-auto mt-6">
    <div
      class="bg-[#f8f9ff] dark:bg-gray-900/50 rounded-4xl border border-[#e1e7f5] dark:border-gray-800 overflow-hidden shadow-sm"
    >
      <button
        @click="isOpen = !isOpen"
        class="w-full flex items-center justify-between p-6 md:p-8 text-left transition-colors hover:bg-[#f0f4ff] dark:hover:bg-gray-800/80"
      >
        <div class="flex items-center gap-4">
          <div
            class="size-8 md:size-12 rounded-full bg-red-500 flex items-center justify-center shrink-0 shadow-lg shadow-[#4279ce]/20"
          >
            <UIcon name="i-ph-info-bold" class="w-6 h-6 text-white" />
          </div>
          <h2
            class="text-lg md:text-2xl font-bold text-[#4a4a4a] dark:text-gray-100"
          >
            Чому я не стрижу котиків?
          </h2>
        </div>
        <UIcon
          name="i-ph-caret-down-bold"
          class="w-6 h-6 text-[#4279ce] transition-transform duration-300"
          :class="{ 'rotate-180': isOpen }"
        />
      </button>

      <div v-show="isOpen" class="px-6 pb-8 md:px-12 md:pb-12">
        <div class="space-y-8">
          <div
            class="p-4 rounded-2xl bg-white dark:bg-gray-800 border-l-4 border-[#4279ce] shadow-sm"
          >
            <p class="text-[#4a4a4a] dark:text-gray-200 font-medium italic">
              Важливо! Я за гуманний грумінг і збереження здоровʼя та довіри
              хвостика — тому я не стрижу котиків.
            </p>
          </div>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
            <div class="space-y-2">
              <div class="flex items-center gap-2 text-[#4279ce] font-bold">
                <span class="text-xl">🔵</span>
                <h3>Шерсть — природний захист</h3>
              </div>
              <p class="text-sm text-[#7a7a7a] dark:text-gray-400 pl-8">
                Вона відповідає за терморегуляцію та захищає шкіру від
                перегріву, холоду й подразнень.
              </p>
            </div>

            <div class="space-y-2">
              <div class="flex items-center gap-2 text-[#4279ce] font-bold">
                <span class="text-xl">🔵</span>
                <h3>Порушення росту шерсті</h3>
              </div>
              <p class="text-sm text-[#7a7a7a] dark:text-gray-400 pl-8">
                Після стрижки шерсть може відростати нерівномірно, змінювати
                структуру та швидше звалюватися в ковтуни.
              </p>
            </div>

            <div class="space-y-2">
              <div class="flex items-center gap-2 text-[#4279ce] font-bold">
                <span class="text-xl">🔵</span>
                <h3>Сильний стрес</h3>
              </div>
              <p class="text-sm text-[#7a7a7a] dark:text-gray-400 pl-8">
                Стрижка є неприродною процедурою для котів і часто викликає
                страх та втрату довіри до грумінгу.
              </p>
            </div>

            <div class="space-y-2">
              <div class="flex items-center gap-2 text-[#4279ce] font-bold">
                <span class="text-xl">🔵</span>
                <h3>Ризик травм</h3>
              </div>
              <p class="text-sm text-[#7a7a7a] dark:text-gray-400 pl-8">
                Котяча шкіра дуже тонка й чутлива, тому під час стрижки зростає
                ризик порізів.
              </p>
            </div>
          </div>

          <hr class="border-dashed border-gray-300 dark:border-gray-700" />

          <div class="space-y-4">
            <h4
              class="text-center font-bold text-[#4a4a4a] dark:text-gray-200 uppercase tracking-widest text-sm"
            >
              Коли можливе часткове вистригання
            </h4>
            <div class="flex flex-col md:flex-row gap-4 justify-center">
              <div
                class="bg-amber-50 dark:bg-amber-950/20 p-5 rounded-2xl border border-amber-100 dark:border-amber-900/30 flex-1"
              >
                <div
                  class="flex items-center gap-2 text-amber-800 dark:text-amber-400 font-bold mb-2"
                >
                  <UIcon name="i-ph-scissors-bold" />
                  <span>Лише за необхідності</span>
                </div>
                <p
                  class="text-sm text-amber-700/90 dark:text-amber-500/80 leading-relaxed"
                >
                  Якщо ковтуни неможливо безпечно вичесати, я виконую часткове,
                  локальне вистригання — обережно та без шкоди для котика.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
