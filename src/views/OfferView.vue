<script setup>
import photo from "@/assets/img/2.jpg";

const mainServices = [
  "usługi geodezyjne i kartograficzne,",
  "pośrednictwo w obrocie nieruchomościami,",
  "przygotowanie dokumentacji środowiskowej (karty informacyjne przedsięwzięcia/ raporty środowiskowe/ analizy środowiskowe/ analizy akustyczne/ itp.),",
  "przygotowanie dokumentacji do decyzji o warunkach zabudowy i decyzji pozwolenia na budowę."
];

const additionalServices = [
  { title: "Mapy projektowe", desc: "Forma analogowa i numeryczna pod budowę obiektów, sieci i przyłączy.", icon: "fa-regular fa-map" },
  { title: "Tyczenia i realizacje", desc: "Tyczenia obiektów budowlanych, liniowych, sieci i przyłączy.", icon: "fa-solid fa-globe" },
  { title: "Inwentaryzacje", desc: "Powykonawcze inwentaryzacje obiektów budowlanych i sieci.", icon: "fa-solid fa-map-location-dot" },
  { title: "Podziały nieruchomości", desc: "Działki zurbanizowane, rolne oraz leśne.", icon: "fa-solid fa-object-ungroup" },
  { title: "Połączenia działek", desc: "Łączenie działek ewidencyjnych w jedną całość.", icon: "fa-solid fa-object-group" },
  { title: "Rozgraniczenia", desc: "Ustalanie i wznawianie granic nieruchomości.", icon: "fa-solid fa-border-top-left" },
  { title: "Znaki graniczne", desc: "Wznowienia znaków i wyznaczanie punktów granicznych.", icon: "fa-solid fa-location-dot" },
  { title: "Dokumentacja prawna", desc: "Mapy do celów prawnych, służebności i inne opracowania.", icon: "fa-solid fa-file-contract" },
  { title: "Obsługa inwestycji", desc: "Kompleksowa obsługa geodezyjna dużych i małych projektów.", icon: "fa-solid fa-road-barrier" },
  { title: "Badanie stanu prawnego", desc: "Szczegółowa analiza ksiąg wieczystych i dokumentacji.", icon: "fa-solid fa-magnifying-glass" },
  { title: "Wykazy synchronizacyjne", desc: "Sporządzanie dokumentacji do ujawnienia w KW.", icon: "fa-solid fa-list-check" },
  { title: "Inne opracowania", desc: "Wszelkie pozostałe prace geodezyjne i kartograficzne.", icon: "fa-solid fa-compass-drafting" }
];
</script>

<template>
  <!-- Header Section -->
  <section class="bg-navyBlue py-20 text-white text-center relative overflow-hidden">
    <!-- Decorative Elements -->
    <div class="absolute -top-10 -right-10 w-64 h-64 bg-yellowMain/10 rounded-full"></div>
    <div class="absolute -bottom-10 -left-10 w-96 h-96 bg-white/5 rounded-full"></div>
    
    <div class="container mx-auto px-6 relative z-10">
      <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold font-Rubik mb-4">Nasza oferta</h1>
      <p class="text-yellowMain uppercase tracking-widest font-bold max-w-2xl mx-auto">Pracownia Geodezyjna Przemysław Junkiert</p>
      <div class="w-24 h-1.5 bg-yellowMain mx-auto mt-8 rounded-full"></div>
    </div>
  </section>

  <!-- Main Offer Section -->
  <section class="py-20">
    <div class="container mx-auto px-6 max-w-6xl">
      <div class="flex flex-col lg:flex-row items-center gap-12 mb-24">
        <div class="lg:w-1/2 space-y-6">
          <div class="inline-block px-4 py-1 bg-yellowMain text-navyBlue font-bold rounded-full text-sm uppercase mb-2">Oferta Główna</div>
          <h2 class="text-3xl md:text-4xl font-bold font-Rubik text-navyBlue">Kompleksowe usługi dla Twojej inwestycji</h2>
          <p class="text-gray-600 leading-relaxed">Specjalizujemy się w szerokim zakresie prac geodezyjnych, od prostych pomiarów po zaawansowane analizy środowiskowe.</p>
          
          <ul class="space-y-4">
            <li v-for="(item, index) in mainServices" :key="index" class="flex gap-4">
              <i class="pi pi-check-circle text-yellowMain text-xl flex-shrink-0 mt-1"></i>
              <span class="text-gray-700 font-medium">{{ item }}</span>
            </li>
          </ul>
        </div>
        <div class="lg:w-1/2 relative">
          <div class="absolute -top-4 -left-4 w-24 h-24 bg-yellowMain/20 rounded-full blur-2xl"></div>
          <img :src="photo" alt="Praca geodety" class="rounded-2xl shadow-2xl relative z-10 border-8 border-white" />
          <div class="absolute -bottom-6 -right-6 w-32 h-32 border-4 border-yellowMain rounded-2xl -z-10"></div>
        </div>
      </div>

      <!-- Additional Services Grid -->
      <div class="text-center mb-12">
        <h2 class="text-3xl font-bold font-Rubik text-navyBlue">Szczegółowy zakres prac</h2>
        <div class="w-20 h-1.5 bg-yellowMain mx-auto mt-4 rounded-full"></div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="(service, index) in additionalServices" :key="index" 
             class="p-8 bg-white border border-gray-100 rounded-2xl shadow-sm hover:shadow-xl transition-all duration-300 hover:border-yellowMain group flex flex-col items-center text-center">
          <div class="w-16 h-16 bg-gray-50 rounded-2xl flex items-center justify-center mb-6 group-hover:bg-yellowMain transition-colors">
            <i :class="[service.icon, 'text-2xl text-navyBlue group-hover:scale-110 transition-transform']"></i>
          </div>
          <h3 class="text-xl font-bold font-Rubik text-navyBlue mb-3">{{ service.title }}</h3>
          <p class="text-sm text-gray-500 leading-relaxed">{{ service.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.container {
  max-width: 1200px;
}
.shadow-sm {
  box-shadow: 0 10px 30px -15px rgba(0, 0, 0, 0.05);
}
</style>
