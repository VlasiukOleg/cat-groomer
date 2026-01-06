<script setup lang="ts">
const contactInfo = [
  { icon: "i-heroicons-phone", text: "(555) 123-4567", label: "Телефон" },
  {
    icon: "i-heroicons-envelope",
    text: "hello@catgrooming.com",
    label: "Email",
  },
  { icon: "i-heroicons-map-pin", text: "вул. Котяча, 123", label: "Адреса" },
];

const state = reactive({
  name: undefined,
  email: undefined,
  catName: undefined,
  message: undefined,
});
</script>

<template>
  <section id="contacts" class="py-16 md:py-24 bg-white dark:bg-gray-950">
    <UContainer>
      <div class="max-w-4xl mx-auto text-center mb-12 md:mb-16 space-y-4">
        <h2
          class="text-3xl md:text-5xl font-bold text-[#4a4a4a] dark:text-gray-100"
        >
          Зв'яжіться з Нами
        </h2>
        <p class="text-lg md:text-xl text-[#7a7a7a] dark:text-gray-400 px-4">
          Готові побалувати свого котика? Ми будемо раді почути від вас.
        </p>
      </div>

      <div class="max-w-4xl mx-auto">
        <div class="grid sm:grid-cols-3 gap-6 md:gap-8 mb-12">
          <div
            v-for="(item, index) in contactInfo"
            :key="index"
            class="group text-center space-y-3 p-4 rounded-2xl transition-all duration-300 hover:bg-[#f8f6f4] dark:hover:bg-gray-900"
          >
            <div
              class="w-12 h-12 md:w-16 md:h-16 rounded-full bg-[#f8f6f4] dark:bg-gray-800 flex items-center justify-center mx-auto group-hover:scale-110 group-hover:bg-[#e8d7c8] transition-all duration-300"
            >
              <UIcon
                :name="item.icon"
                class="w-6 h-6 md:w-8 md:h-8 text-[#8b6f5c] dark:text-cameo-300"
              />
            </div>
            <div>
              <p class="text-xs uppercase tracking-widest text-[#aaa] mb-1">
                {{ item.label }}
              </p>
              <p
                class="text-sm md:text-base font-medium text-[#4a4a4a] dark:text-gray-200"
              >
                {{ item.text }}
              </p>
            </div>
          </div>
        </div>

        <div
          class="bg-[#f8f6f4] dark:bg-gray-900 rounded-[2rem] p-6 md:p-12 shadow-sm"
        >
          <form class="space-y-6" @submit.prevent>
            <div class="grid md:grid-cols-2 gap-6">
              <UInput
                v-model="state.name"
                placeholder="Ваше Ім'я"
                size="xl"
                variant="none"
                class="bg-white dark:bg-gray-800 rounded-full px-4 shadow-sm"
              />
              <UInput
                v-model="state.email"
                type="email"
                placeholder="Електронна Адреса"
                size="xl"
                variant="none"
                class="bg-white dark:bg-gray-800 rounded-full px-4 shadow-sm"
              />
              <UInput
                v-model="state.catName"
                placeholder="Ім'я Вашого Кота"
                size="xl"
                variant="none"
                class="bg-white dark:bg-gray-800 rounded-full px-4 shadow-sm"
              />
            </div>

            <UTextarea
              v-model="state.message"
              placeholder="Розкажіть нам про ваші потреби в грумінгу..."
              size="xl"
              variant="none"
              :rows="5"
              class="bg-white dark:bg-gray-800 rounded-4xl px-4 py-2 shadow-sm w-full"
              autoresize
            />

            <UButton
              type="submit"
              label="Надіслати Повідомлення"
              size="xl"
              block
              class="rounded-full py-4 text-lg font-bold transition-all duration-300 bg-cameo-400 hover:bg-[#c4a590] hover:scale-[1.02] active:scale-[0.98] shadow-lg shadow-primary-500/20"
            />
          </form>
        </div>
      </div>
    </UContainer>
  </section>
</template>
