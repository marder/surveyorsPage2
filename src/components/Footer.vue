<script setup>
import logo from "@/assets/img/logo_junkiert.png";
</script>

<template>
  <footer class="bg-navyBlue text-white py-12">
    <div class="container mx-auto px-6">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-12">
        <!-- Section 1: Brand/Logo -->
        <div class="flex flex-col items-center md:items-start text-center md:text-left">
          <img :src="logo" alt="Logo" class="w-32 mb-4 bg-white p-2 rounded shadow-sm" />
          <h2 class="text-xl font-bold font-Rubik mb-2 text-yellowMain">Pracownia Geodezyjna</h2>
          <p class="text-sm text-gray-400 max-w-xs">
            Profesjonalne usługi geodezyjne i kartograficzne. Ponad wieloletnie doświadczenie w branży.
          </p>
        </div>

        <!-- Section 2: Quick Links -->
        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-lg font-bold font-Rubik mb-4 border-b-2 border-yellowMain pb-1">Nawigacja</h3>
          <ul class="space-y-2 text-center md:text-left">
            <li>
              <a href="/" class="text-gray-300 hover:text-yellowMain transition-colors duration-300">Strona Główna</a>
            </li>
            <li>
              <a href="/about" class="text-gray-300 hover:text-yellowMain transition-colors duration-300">O nas</a>
            </li>
            <li>
              <a href="/offer" class="text-gray-300 hover:text-yellowMain transition-colors duration-300">Oferta</a>
            </li>
            <li>
              <a href="/contact" class="text-gray-300 hover:text-yellowMain transition-colors duration-300">Kontakt</a>
            </li>
          </ul>
        </div>

        <!-- Section 3: Contact Info -->
        <div class="flex flex-col items-center md:items-start">
          <h3 class="text-lg font-bold font-Rubik mb-4 border-b-2 border-yellowMain pb-1">Kontakt</h3>
          <ul class="space-y-4 text-center md:text-left">
            <li class="flex items-center space-x-3 justify-center md:justify-start">
              <i class="pi pi-map-marker text-yellowMain"></i>
              <span class="text-gray-300 text-sm">ul. Legionów Polskich 1/11, 62-700 Turek</span>
            </li>
            <li class="flex items-center space-x-3 justify-center md:justify-start">
              <i class="pi pi-phone text-yellowMain"></i>
              <a href="tel:+48603386856" class="text-gray-300 hover:text-yellowMain transition-colors text-sm">+48 603-386-856</a>
            </li>
            <li class="flex items-center space-x-3 justify-center md:justify-start">
              <i class="pi pi-envelope text-yellowMain"></i>
              <a href="mailto:biuro.junkiert@gmail.com" class="text-gray-300 hover:text-yellowMain transition-colors text-sm">biuro.junkiert@gmail.com</a>
            </li>
          </ul>
        </div>
      </div>

      <!-- Bottom Bar -->
      <div class="border-t border-gray-700 mt-12 pt-8 flex flex-col md:flex-row justify-between items-center text-xs text-gray-500">
        <p>&copy; {{ new Date().getFullYear() }} Pracownia Geodezyjna Przemysław Junkiert. Wszelkie prawa zastrzeżone.</p>
        <div class="mt-4 md:mt-0 text-center md:text-right">
          <p>Projekt i wykonanie: <span class="text-gray-400">1337studio</span></p>
          <p>Zdjęcia: <a href="https://www.freepik.com" target="_blank" class="hover:text-yellowMain underline decoration-dotted">freepik.com</a></p>
        </div>
      </div>
    </div>
  </footer>
</template>
