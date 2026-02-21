<script setup>
import Contact from "@/components/Contact.vue";
</script>

<template>
  <div class="bg-white min-h-screen">
    <!-- Page Header -->
    <section class="bg-navyBlue py-24 text-white text-center relative overflow-hidden">
      <!-- Decorative Elements -->
      <div class="absolute -top-10 -right-10 w-64 h-64 bg-yellowMain/10 rounded-full"></div>
      <div class="absolute -bottom-10 -left-10 w-96 h-96 bg-white/5 rounded-full"></div>
      
      <div class="container mx-auto px-6 relative z-10">
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold font-Rubik mb-4">Kontakt</h1>
        <p class="text-yellowMain uppercase tracking-widest font-bold max-w-2xl mx-auto">
          Pracownia Geodezyjna JUNKIERT INVESTMENT
        </p>
        <div class="w-24 h-1.5 bg-yellowMain mx-auto mt-8 rounded-full"></div>
      </div>
    </section>

    <!-- Main Contact Component -->
    <Contact />

    <!-- Additional Info Section -->
    <section class="pb-24 bg-gray-50">
      <div class="container mx-auto px-6 max-w-4xl">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-12 text-center md:text-left">
          <div class="space-y-4">
            <h3 class="text-2xl font-bold text-navyBlue font-Rubik flex items-center justify-center md:justify-start gap-3">
              <i class="pi pi-info-circle text-yellowMain"></i>
              Ważne informacje
            </h3>
            <p class="text-gray-600 leading-relaxed">
              Dla wygody naszych klientów, preferujemy kontakt telefoniczny przed wizytą w biurze. Pomoże to nam przygotować niezbędne dokumenty i zarezerwować odpowiednią ilość czasu na konsultację.
            </p>
          </div>
          <div class="space-y-4">
            <h3 class="text-2xl font-bold text-navyBlue font-Rubik flex items-center justify-center md:justify-start gap-3">
              <i class="pi pi-map text-yellowMain"></i>
              Obszar działania
            </h3>
            <p class="text-gray-600 leading-relaxed">
              Świadczymy usługi geodezyjne głównie na terenie powiatu tureckiego, kolskiego oraz konińskiego. W przypadku większych inwestycji działamy na terenie całego województwa wielkopolskiego.
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.container {
  max-width: 1200px;
}
</style>
