<script setup>
import photo from "@/assets/img/2.jpg";

const team = [
  {
    name: "Przemysław Junkiert",
    role: "Właściciel Pracowni Geodezyjnej JUNKIERT INVESTMENT",
    desc: "Magister gospodarki nieruchomościami, Inżynier geodeta. Geodeta uprawniony w zakresie 1 i 2 (uprawnienia GUGiK 23442). Biegły Sądowy przy Sądzie Okręgowym w Koninie. Pośrednik w obrocie nieruchomości (licencja zawodowa Ministra Infrastruktury nr 14488). Kierownik prac geodezyjnych.",
    tags: ["Magister", "Inżynier", "Uprawnienia 1 i 2", "Biegły Sądowy", "Pośrednik", "Kierownik"]
  },
  {
    name: "Julita Szalewska",
    role: "Współwłaściciel Pracowni Geodezyjnej JUNKIERT INVESTMENT",
    desc: "Magister gospodarki nieruchomościami, Inżynier geodeta. Geodeta uprawniony w zakresie 1 i 2 (uprawnienia GUGiK 23442). Biegły Sądowy przy Sądzie Okręgowym w Koninie. Pośrednik w obrocie nieruchomości (licencja zawodowa Ministra Infrastruktury nr 14488). Kierownik prac geodezyjnych.",
    tags: ["Magister", "Inżynier", "Uprawnienia 1 i 2", "Biegły Sądowy", "Pośrednik", "Kierownik"]
  },
  {
    name: "Malwina Rosiak",
    role: "Specjalista ds. Geodezji i Gospodarki Nieruchomościami",
    desc: "Magister gospodarki nieruchomościami, Inżynier geodeta. Geodeta uprawniony w zakresie 1 i 2 (uprawnienia GUGiK 23442). Biegły Sądowy przy Sądzie Okręgowym w Koninie. Pośrednik w obrocie nieruchomości (licencja zawodowa Ministra Infrastruktury nr 14488). Kierownik prac geodezyjnych.",
    tags: ["Magister", "Inżynier", "Uprawnienia 1 i 2", "Biegły Sądowy", "Pośrednik", "Kierownik"]
  }
];
</script>

<template>
  <!-- Hero Section -->
  <section class="bg-navyBlue py-20 text-white text-center relative overflow-hidden">
    <div class="absolute -top-10 -right-10 w-64 h-64 bg-yellowMain/10 rounded-full"></div>
    <div class="absolute -bottom-10 -left-10 w-96 h-96 bg-white/5 rounded-full"></div>
    
    <div class="container mx-auto px-6 relative z-10">
      <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold font-Rubik mb-4">Nasz zespół</h1>
      <p class="text-yellowMain uppercase tracking-widest font-bold max-w-2xl mx-auto">
        Poznaj specjalistów, którzy stoją za sukcesem Twoich inwestycji. Nasza wiedza i doświadczenie to Twoje bezpieczeństwo.
      </p>
    </div>
  </section>

  <!-- Team Section -->
  <section class="py-24 bg-gray-50">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 lg:grid-cols-1 gap-16 max-w-5xl mx-auto">
        <div v-for="(member, index) in team" :key="index" 
             class="flex flex-col md:flex-row items-center gap-8 md:gap-12 bg-white p-8 md:p-12 rounded-3xl shadow-xl hover:shadow-2xl transition-all duration-500 border border-gray-100 group">
          
          <!-- Member Image -->
          <div class="w-48 h-48 md:w-64 md:h-64 flex-shrink-0 relative">
            <div class="absolute inset-0 bg-yellowMain rounded-2xl transform rotate-3 group-hover:rotate-6 transition-transform"></div>
            <img :src="photo" :alt="member.name" class="relative z-10 w-full h-full object-cover rounded-2xl shadow-lg border-4 border-white grayscale group-hover:grayscale-0 transition-all duration-500" />
            
            <!-- Professional Badge -->
            <div class="absolute -bottom-4 -right-4 bg-navyBlue text-white p-3 rounded-xl z-20 shadow-lg">
              <i class="pi pi-verified text-yellowMain text-xl"></i>
            </div>
          </div>

          <!-- Member Details -->
          <div class="flex-grow space-y-6 text-center md:text-left">
            <div>
              <h2 class="text-3xl font-bold text-navyBlue font-Rubik group-hover:text-yellowMain transition-colors">{{ member.name }}</h2>
              <p class="text-navyBlue/70 font-semibold uppercase text-sm tracking-wider mt-1">{{ member.role }}</p>
            </div>
            
            <p class="text-gray-600 leading-relaxed text-lg italic">
              "{{ member.desc.split('.')[0] }}. {{ member.desc.split('.')[1] }}."
            </p>

            <div class="flex flex-wrap justify-center md:justify-start gap-2">
              <span v-for="tag in member.tags" :key="tag" 
                    class="bg-gray-50 text-gray-700 px-3 py-1 rounded-lg text-xs font-bold border border-gray-100 uppercase tracking-tighter">
                {{ tag }}
              </span>
            </div>

            <!-- Qualification Icons -->
            <div class="grid grid-cols-2 sm:grid-cols-3 gap-4 pt-4 border-t border-gray-50">
              <div class="flex items-center gap-2 text-sm text-gray-500 font-medium">
                <i class="pi pi-briefcase text-yellowMain"></i>
                <span>Uprawnienia GUGiK</span>
              </div>
              <div class="flex items-center gap-2 text-sm text-gray-500 font-medium">
                <i class="pi pi-shield text-yellowMain"></i>
                <span>Biegły Sądowy</span>
              </div>
              <div class="flex items-center gap-2 text-sm text-gray-500 font-medium">
                <i class="pi pi-map text-yellowMain"></i>
                <span>Pośrednik</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Certifications Section -->
  <section class="py-20 bg-white">
    <div class="container mx-auto px-6 text-center">
      <h3 class="text-2xl font-bold text-navyBlue font-Rubik mb-12">Nasze kompetencje potwierdzają licencje</h3>
      <div class="flex flex-wrap justify-center gap-8 md:gap-16 opacity-60 grayscale hover:grayscale-0 transition-all duration-500">
        <div class="flex flex-col items-center gap-3 max-w-[150px]">
           <div class="w-20 h-20 bg-gray-50 rounded-full flex items-center justify-center border border-gray-100">
             <i class="fa-solid fa-map-location-dot text-3xl text-navyBlue"></i>
           </div>
           <span class="text-xs font-bold uppercase tracking-tighter leading-tight">Główny Urząd Geodezji i Kartografii</span>
        </div>
        <div class="flex flex-col items-center gap-3 max-w-[150px]">
           <div class="w-20 h-20 bg-gray-50 rounded-full flex items-center justify-center border border-gray-100">
             <i class="fa-solid fa-building-columns text-3xl text-navyBlue"></i>
           </div>
           <span class="text-xs font-bold uppercase tracking-tighter leading-tight">Ministerstwo Infrastruktury</span>
        </div>
        <div class="flex flex-col items-center gap-3 max-w-[150px]">
           <div class="w-20 h-20 bg-gray-50 rounded-full flex items-center justify-center border border-gray-100">
             <i class="fa-solid fa-scale-balanced text-3xl text-navyBlue"></i>
           </div>
           <span class="text-xs font-bold uppercase tracking-tighter leading-tight">Sąd Okręgowy w Koninie</span>
        </div>
        <div class="flex flex-col items-center gap-3 max-w-[150px]">
           <div class="w-20 h-20 bg-gray-50 rounded-full flex items-center justify-center border border-gray-100">
             <i class="fa-solid fa-id-card-clip text-3xl text-navyBlue"></i>
           </div>
           <span class="text-xs font-bold uppercase tracking-tighter leading-tight">Polska Federacja Rynku Nieruchomości</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.container {
  max-width: 1200px;
}
</style>
