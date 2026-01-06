<script setup lang="ts">
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
      <div
        class="flex flex-col md:grid md:grid-cols-2 gap-8 md:gap-12 items-center"
      >
        <div class="space-y-4 md:space-y-6 text-center md:text-left order-1">
          <h1
            class="text-4xl md:text-5xl lg:text-6xl text-[#4a4a4a] dark:text-gray-100 font-bold leading-tight"
          >
            Ніжний догляд для вашого котика
          </h1>

          <p class="text-lg md:text-xl text-[#7a7a7a] dark:text-gray-400">
            Професійний котячий грумінг, створений з турботою про комфорт,
            безпеку та емоційний стан вашого кота. Без стресу, поспіху та
            насильницьких методів — лише уважний, індивідуальний підхід до
            кожного хвостатого клієнта.
          </p>

          <div class="hidden md:block pt-4">
            <UButton
              size="xl"
              label="Записатися на Прийом"
              @click="scrollToContact"
              variant="solid"
              class="rounded-full bg-cameo-400 hover:bg-[#c4a590] p-5 text-xl"
            />
          </div>
        </div>

        <div class="relative group order-2">
          <div
            class="absolute -z-10 inset-0 bg-primary-200/40 dark:bg-primary-900/20 blur-3xl rounded-full scale-110 group-hover:scale-125 transition-transform duration-700"
          ></div>

          <div
            class="relative h-[400px] md:h-[550px] w-full max-w-[350px] md:max-w-[400px] mx-auto rounded-[2rem] overflow-hidden shadow-2xl transition-transform duration-500 hover:scale-[1.02] border-4 border-white dark:border-gray-800"
          >
            <video
              autoplay
              muted
              loop
              playsinline
              preload="auto"
              class="w-full h-full object-cover"
            >
              <source src="/video/cat-hero.MOV" type="video/mp4" />
              Ваш браузер не підтримує відео.
            </video>
            <div
              class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent pointer-events-none"
            ></div>
          </div>
        </div>

        <div class="block md:hidden order-3 text-center w-full pt-4">
          <UButton
            size="xl"
            label="Записатися на Прийом"
            @click="scrollToContact"
            variant="solid"
            class="rounded-full bg-cameo-400 hover:bg-[#c4a590] p-5 text-xl"
          />
        </div>
      </div>
    </UContainer>
  </section>
</template>

<style scoped>
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
