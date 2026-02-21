<script setup>
import { VueperSlides, VueperSlide } from "vueperslides";
import "vueperslides/dist/vueperslides.css";
import { RouterLink } from "vue-router";

import slide1 from "@/assets/img/slide1.jpg";
import slide2 from "@/assets/img/slide2.jpg";
import slide3 from "@/assets/img/slide3.jpg";
import slide4 from "@/assets/img/slide4.jpg";

const slides = [
  {
    label: "Doświadczenie i Precyzja",
    title: "Tradycja w Geodezji",
    content: "Profesjonalne usługi oparte na wieloletniej praktyce przekazywanej z pokolenia na pokolenie.",
    image: slide1,
  },
  {
    label: "Nowoczesność",
    title: "Innowacyjne Pomiary",
    content: "Wykorzystujemy najnowszy sprzęt, gwarantując najwyższą dokładność i szybki czas realizacji.",
    image: slide2,
  },
  {
    label: "Bezpieczeństwo Prawne",
    title: "Eksperci od Nieruchomości",
    content: "Specjalizujemy się w geodezji prawnej, podziałach i trudnych sprawach granicznych.",
    image: slide3,
  },
  {
    label: "Kompleksowa Obsługa",
    title: "Twoja Inwestycja",
    content: "Zapewniamy pełne wsparcie geodezyjne na każdym etapie budowy – od projektu po odbiór.",
    image: slide4,
  },
];
</script>

<template>
  <section class="relative">
    <vueper-slides 
      autoplay 
      fade 
      :touchable="true" 
      :arrows="true" 
      :bullets="true"
      fixed-height="650px"
      :breakpoints="{
        768: { fixedHeight: '520px', draggingDistance: 50 }
      }"
      class="no-shadow"
      :duration="6000"
    >
      <vueper-slide
        v-for="(slide, i) in slides"
        :key="i"
        :image="slide.image"
      >
        <template #content>
          <!-- Darker Overlay for maximum contrast (70% opacity) -->
          <div class="absolute inset-0 bg-navyBlue/70 flex items-center justify-center text-center px-6">
            <div class="max-w-4xl space-y-4 md:space-y-6">
              
              <!-- Top Label (Yellow Accent) -->
              <span class="inline-block text-yellowMain font-bold uppercase tracking-[0.2em] md:tracking-[0.3em] text-xs md:text-base mb-1 md:mb-2 drop-shadow-lg">
                {{ slide.label }}
              </span>

              <!-- Big Title (White) -->
              <h1 class="text-white text-3xl md:text-7xl lg:text-8xl font-bold font-Rubik leading-tight drop-shadow-2xl">
                {{ slide.title }}
              </h1>

              <!-- Description -->
              <p class="text-white text-base md:text-2xl font-medium max-w-2xl mx-auto leading-relaxed drop-shadow-xl opacity-90 px-4 md:px-0">
                {{ slide.content }}
              </p>

              <!-- Buttons -->
              <div class="pt-6 md:pt-10 flex flex-col sm:flex-row justify-center gap-4 md:gap-5">
                <RouterLink to="/offer" class="px-8 md:px-10 py-3 md:py-4 bg-yellowMain text-navyBlue font-extrabold rounded-full shadow-2xl hover:bg-white hover:-translate-y-1 transition-all duration-300 uppercase tracking-widest text-[10px] md:text-xs border-2 border-yellowMain">
                  Nasza Oferta
                </RouterLink>
                <RouterLink to="/contact" class="px-8 md:px-10 py-3 md:py-4 bg-transparent text-white border-2 border-white/50 font-extrabold rounded-full shadow-xl hover:bg-white hover:text-navyBlue hover:border-white hover:-translate-y-1 transition-all duration-300 uppercase tracking-widest text-[10px] md:text-xs backdrop-blur-sm">
                  Skontaktuj się
                </RouterLink>
              </div>

            </div>
          </div>
        </template>
      </vueper-slide>

      <!-- Navigation UI -->
      <template #arrow-left>
        <div class="p-3 md:p-4 bg-white/10 hover:bg-yellowMain transition-all rounded-full backdrop-blur-md text-white hover:text-navyBlue hidden md:block border border-white/20">
          <i class="pi pi-arrow-left text-lg md:text-xl"></i>
        </div>
      </template>
      <template #arrow-right>
        <div class="p-3 md:p-4 bg-white/10 hover:bg-yellowMain transition-all rounded-full backdrop-blur-md text-white hover:text-navyBlue hidden md:block border border-white/20">
          <i class="pi pi-arrow-right text-lg md:text-xl"></i>
        </div>
      </template>
    </vueper-slides>
  </section>
</template>

<style scoped>
/* Scoped Shadow only for Carousel Content to ensure readability */
.max-w-4xl h1, 
.max-w-4xl p, 
.max-w-4xl span {
  text-shadow: 0 4px 12px rgba(0, 0, 0, 0.6);
}

:deep(.vueperslides__bullet .default) {
  background-color: rgba(255, 255, 255, 0.3);
  border: none;
  width: 8px;
  height: 8px;
  margin: 0 6px;
  transition: all 0.4s ease;
}

:deep(.vueperslides__bullet--active .default) {
  background-color: #ff9900; /* yellowMain */
  width: 25px;
  border-radius: 10px;
}

:deep(.vueperslides__bullets) {
  bottom: 40px;
}

@media (max-width: 768px) {
  :deep(.vueperslides__bullets) {
    bottom: 35px;
  }
}
</style>
