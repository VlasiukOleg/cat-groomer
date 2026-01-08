<script setup lang="ts">
const contactInfo = [
  { 
    icon: "i-ph-phone", 
    text: "(098) 914-79-04", 
    label: "Телефон",
    href: "tel:+380989147904" 
  },
  {
    icon: "i-ph-instagram-logo", 
    text: "rimmagroomer", 
    label: "Instagram",
    href: "https://www.instagram.com/rimmagroomer?igsh=MWV3dWUyaDVmeWdhcw=="
  },
  { 
    icon: "i-ph-map-pin", 
    text: "Тютюнника, 56", 
    label: "Адреса",
    href: "https://www.google.com/maps/search/?api=1&query=вулиця+Василя+Тютюнника,+56,+Київ"
  },
];

const state = reactive({
  name: undefined,
  email: undefined,
  catName: undefined,
  message: undefined,
});
</script>

<template>
  <section id="contacts" class="py-8 md:py-24 bg-white dark:bg-gray-950">
    <UContainer>
      <div class="max-w-4xl mx-auto text-center mb-8 md:mb-16 space-y-2">
        <h2 class="text-3xl md:text-5xl font-bold text-[#4a4a4a] dark:text-gray-100">
          Зв'яжіться з Нами
        </h2>
        <p class="text-sm md:text-xl text-[#7a7a7a] dark:text-gray-400 px-4">
          Готові побалувати свого котика? Ми завжди на зв'язку.
        </p>
      </div>

      <div class="max-w-4xl mx-auto">
        <div class="grid grid-cols-3 gap-1 sm:gap-4 md:gap-8 mb-10 md:mb-16">
          <a
            v-for="(item, index) in contactInfo"
            :key="index"
            :href="item.href"
            target="_blank"
            rel="noopener noreferrer"
            class="group text-center space-y-2 p-1 md:p-6 rounded-2xl transition-all duration-300 hover:bg-[#f8f6f4] dark:hover:bg-gray-900"
          >
            <div
              class="w-10 h-10 md:w-16 md:h-16 rounded-xl bg-[#f8f6f4] dark:bg-gray-800 flex items-center justify-center mx-auto group-hover:scale-110 group-hover:bg-[#e8d7c8] transition-all duration-300 shadow-sm"
            >
              <UIcon
                :name="item.icon"
                class="w-5 h-5 md:w-8 md:h-8 text-[#8b6f5c] dark:text-cameo-300"
              />
            </div>
            <div class="overflow-hidden px-1">
              <p class="text-xs uppercase tracking-tighter md:tracking-[0.2em] text-[#aaa] mb-0.5 font-semibold">
                {{ item.label }}
              </p>
              <p class="text-xs md:text-base font-bold text-[#4a4a4a] dark:text-gray-200 truncate group-hover:text-[#8b6f5c]">
                {{ item.text }}
              </p>
            </div>
          </a>
        </div>

        <div class="bg-[#f8f6f4] dark:bg-gray-900 rounded-[2.5rem] p-6 md:p-12 shadow-sm border border-[#f0edea] dark:border-gray-800">
          <form class="space-y-4 md:space-y-6" @submit.prevent>
            <div class="grid md:grid-cols-3 gap-4">
              <UInput
                v-model="state.name"
                placeholder="Ваше Ім'я"
                size="xl"
                variant="none"
                class="bg-white dark:bg-gray-800 rounded-2xl px-2 shadow-sm border border-gray-100 dark:border-gray-700"
              />
              <UInput
                v-model="state.catName"
                placeholder="Ім'я Котика"
                size="xl"
                variant="none"
                class="bg-white dark:bg-gray-800 rounded-2xl px-2 shadow-sm border border-gray-100 dark:border-gray-700"
              />
              <UInput
                v-model="state.email"
                placeholder="Ваш Контакт"
                size="xl"
                variant="none"
                class="bg-white dark:bg-gray-800 rounded-2xl px-2 shadow-sm border border-gray-100 dark:border-gray-700"
              />
            </div>

            <UTextarea
              v-model="state.message"
              placeholder="Розкажіть нам про ваші побажання..."
              size="xl"
              variant="none"
              :rows="4"
              class="bg-white dark:bg-gray-800 rounded-3xl px-2 py-2 shadow-sm border border-gray-100 dark:border-gray-700 w-full"
              autoresize
            />

            <UButton
              type="submit"
              label="Надіслати Повідомлення"
              size="xl"
              block
              class="rounded-full py-4 md:py-5 text-base md:text-lg font-bold transition-all duration-300 bg-cameo-400 hover:bg-[#3866bd] shadow-md hover:shadow-lg"
            />
          </form>
        </div>
      </div>
    </UContainer>
  </section>
</template>