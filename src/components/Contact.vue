<script setup>
</script>

<template>
  <section id="contact" class="bg-gray-50 py-24">
    <div class="container mx-auto px-6">
      <div class="bg-white rounded-[3rem] shadow-2xl overflow-hidden border border-gray-100">
        <div class="flex flex-col lg:flex-row">
          
          <!-- Contact Info Side -->
          <div class="lg:w-1/2 px-6 py-12 md:p-12 lg:p-20 bg-navyBlue text-white">
            <h2 class="text-yellowMain font-bold uppercase tracking-widest text-sm mb-4">Skontaktuj się z nami</h2>
            <h1 class="text-3xl md:text-5xl font-bold font-Rubik mb-8">Zacznijmy współpracę już dziś</h1>
            <p class="text-gray-300 mb-12 text-lg">
              Masz pytania dotyczące usług geodezyjnych lub potrzebujesz wyceny? 
              Zadzwoń do nas lub napisz – chętnie pomożemy w realizacji Twojej inwestycji.
            </p>

            <div class="space-y-8">
              <!-- Address -->
              <div class="flex items-start gap-4 md:gap-6 group">
                <div class="w-12 h-12 md:w-14 md:h-14 bg-white/10 rounded-2xl flex-shrink-0 flex justify-center items-center group-hover:bg-yellowMain transition-colors duration-300">
                  <i class="pi pi-map-marker text-xl md:text-2xl text-yellowMain group-hover:text-navyBlue"></i>
                </div>
                <div>
                  <h3 class="text-yellowMain font-bold text-base md:text-lg mb-1">Adres biura</h3>
                  <p class="text-gray-200 text-sm md:text-base">ul. Legionów Polskich 1/11</p>
                  <p class="text-gray-200 text-sm md:text-base">62-700 Turek</p>
                </div>
              </div>

              <!-- Phone -->
              <div class="flex items-start gap-4 md:gap-6 group">
                <div class="w-12 h-12 md:w-14 md:h-14 bg-white/10 rounded-2xl flex-shrink-0 flex justify-center items-center group-hover:bg-yellowMain transition-colors duration-300">
                  <i class="pi pi-phone text-xl md:text-2xl text-yellowMain group-hover:text-navyBlue"></i>
                </div>
                <div>
                  <h3 class="text-yellowMain font-bold text-base md:text-lg mb-1">Telefon</h3>
                  <a href="tel:+48603386856" class="text-xl md:text-2xl font-bold hover:text-yellowMain transition-colors whitespace-nowrap">
                    +48 603-386-856
                  </a>
                </div>
              </div>

              <!-- Email -->
              <div class="flex items-start gap-4 md:gap-6 group">
                <div class="w-12 h-12 md:w-14 md:h-14 bg-white/10 rounded-2xl flex-shrink-0 flex justify-center items-center group-hover:bg-yellowMain transition-colors duration-300">
                  <i class="pi pi-envelope text-xl md:text-2xl text-yellowMain group-hover:text-navyBlue"></i>
                </div>
                <div>
                  <h3 class="text-yellowMain font-bold text-base md:text-lg mb-1">E-mail</h3>
                  <a href="mailto:biuro.junkiert@gmail.com" class="text-sm sm:text-base md:text-lg hover:text-yellowMain transition-colors break-all sm:break-normal">
                    biuro.junkiert@gmail.com
                  </a>
                </div>
              </div>
            </div>

            <!-- Working Hours -->
            <div class="mt-16 pt-8 border-t border-white/10">
              <div class="flex items-center gap-3 text-gray-400 font-medium">
                <i class="pi pi-calendar-clock text-yellowMain"></i>
                <span>Zapraszamy: Poniedziałek - Piątek, 9:00 - 11:00</span>
              </div>
            </div>
          </div>

          <!-- Map Side -->
          <div class="lg:w-1/2 min-h-[400px] relative">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2455.4950391636216!2d18.505378878104683!3d52.01607875514588!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x471b18ac09b15555%3A0x83f201ab3ad04c25!2sLegion%C3%B3w%20Polskich%201%2F11%2C%2062-700%20Turek!5e0!3m2!1sen!2spl!4v1736535749725!5m2!1sen!2spl"
              width="100%" height="100%" style="border: 0" allowfullscreen="" loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
              class="absolute inset-0 grayscale contrast-125 brightness-105 hover:grayscale-0 transition-all duration-500"
            ></iframe>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>
