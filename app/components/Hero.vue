<script setup lang="ts">
// Функция скролла
const scrollToContact = () => {
  const element = document.getElementById("contacts");
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
  }
};
</script>

<template>
  <section
    id="hero"
    class="relative min-h-[calc(100vh-64px)] flex items-center justify-center px-4 md:px-6 py-12 md:py-20 bg-[#f8f6f4] dark:bg-gray-900"
  >
    <UContainer>
      <div class="grid md:grid-cols-2 gap-8 md:gap-12 items-center">
        <div class="space-y-4 md:space-y-6 text-center md:text-left">
          <h1
            class="text-4xl md:text-5xl lg:text-6xl text-[#4a4a4a] dark:text-gray-100 font-bold leading-tight"
          >
            Ніжний Догляд для Вашого Котика
          </h1>

          <p class="text-lg md:text-xl text-[#7a7a7a] dark:text-gray-400">
            Професійні послуги грумінгу, розроблені з урахуванням комфорту
            вашого кота. Професійно, без стресу і з індивідуальним підходом до
            кожної унікальної особистості.
          </p>

          <div class="pt-4">
            <UButton
              size="xl"
              label="Записатися на Прийом"
              @click="scrollToContact"
              variant="solid"
              class="ml-2 rounded-full bg-cameo-400 hover:bg-[#c4a590] p-5 text-xl"
            />
          </div>
        </div>

        <div class="relative group">
          <div
            class="absolute -z-10 inset-0 bg-[#d4b5a0]/20 blur-3xl rounded-full scale-110 group-hover:scale-125 transition-transform duration-700"
          ></div>

          <div
            class="relative h-[400px] md:h-[500px] rounded-[2rem] overflow-hidden shadow-2xl transition-transform duration-500 hover:scale-[1.02]"
          >
            <img
              src="https://images.unsplash.com/photo-1704947807029-c75381b64869?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&q=80&w=1080"
              alt="Доглянутий кіт"
              class="w-full h-full object-cover"
            />
          </div>
        </div>
      </div>
    </UContainer>
  </section>
</template>

<style scoped>
/* Добавим плавное появление при загрузке страницы */
#hero {
  animation: fadeIn 1s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
