<script setup>
import logo from "@/assets/img/logo_junkiert.png";
import { RouterLink, useRoute } from "vue-router";
import { ref, onMounted, onUnmounted } from "vue";

const route = useRoute();
const isMenuOpen = ref(false);
const isScrolled = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  // Prevent body scroll when menu is open
  if (isMenuOpen.value) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = '';
  }
};

const closeMenu = () => {
  isMenuOpen.value = false;
  document.body.style.overflow = '';
};

const isActiveLink = (routePath) => {
  return route.path === routePath;
};

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
  document.body.style.overflow = '';
});
</script>

<template>
  <header class="fixed top-0 left-0 w-full z-[100] transition-all duration-300">
    <!-- Top Contact Bar -->
    <div 
      class="bg-navyBlue text-white text-[13px] transition-all duration-300 overflow-hidden hidden md:block"
      :class="isScrolled ? 'h-0 opacity-0' : 'h-10 opacity-100'"
    >
      <div class="container mx-auto px-10 h-full flex justify-between items-center">
        <div class="flex space-x-6 items-center">
          <div class="flex items-center gap-2">
            <i class="pi pi-map-marker text-yellowMain"></i>
            <span>ul. Legionów Polskich 1/11, 62-700 Turek</span>
          </div>
          <div class="flex items-center gap-2">
            <i class="pi pi-calendar-clock text-yellowMain"></i>
            <span>Pn-Pt: 9:00 - 11:00</span>
          </div>
        </div>
        <div class="flex items-center gap-2">
          <i class="pi pi-phone text-yellowMain"></i>
          <a href="tel:+48603386856" class="hover:text-yellowMain transition-colors font-bold">+48 603-386-856</a>
        </div>
      </div>
    </div>

    <!-- Main Navigation -->
    <nav 
      class="w-full transition-all duration-300"
      :class="isScrolled ? 'bg-white/95 backdrop-blur-md py-3 shadow-md' : 'bg-white py-4 md:py-5 shadow-sm'"
    >
      <div class="container mx-auto px-4 md:px-10">
        <div class="flex items-center justify-between">
          <!-- Logo & Title -->
          <RouterLink to="/" class="flex items-center gap-2 md:gap-3" @click="closeMenu">
            <img :src="logo" alt="Logo" class="transition-all duration-300" :class="isScrolled ? 'h-9 md:h-10 lg:h-12' : 'h-10 md:h-12'" />
            <div v-if="!isScrolled" class="leading-tight border-l pl-2 md:pl-3 border-gray-200">
              <span class="block font-bold text-navyBlue text-sm md:text-lg leading-none mb-0.5 md:mb-1">Pracownia Geodezyjna</span>
              <span class="block text-[8px] md:text-[10px] text-gray-500 uppercase tracking-widest font-bold">Przemysław Junkiert</span>
            </div>
            <!-- Smaller title for scrolled state on mobile -->
            <div v-else class="md:hidden leading-tight border-l pl-2 border-gray-200">
              <span class="block font-bold text-navyBlue text-[10px] leading-none uppercase">Geodezja Junkiert</span>
            </div>
          </RouterLink>

          <!-- Desktop Menu -->
          <div class="hidden md:flex items-center space-x-6 lg:space-x-8">
            <RouterLink 
              v-for="link in [
                { path: '/', label: 'Główna' },
                { path: '/offer', label: 'Oferta' },
                { path: '/about', label: 'O nas' }
              ]" 
              :key="link.path"
              :to="link.path"
              class="relative font-Rubik font-medium uppercase text-xs lg:text-sm tracking-wide transition-colors duration-300 group"
              :class="isActiveLink(link.path) ? 'text-navyBlue' : 'text-gray-500 hover:text-navyBlue'"
            >
              {{ link.label }}
              <span 
                class="absolute -bottom-1 left-0 w-0 h-0.5 bg-yellowMain transition-all duration-300 group-hover:w-full"
                :class="{ 'w-full': isActiveLink(link.path) }"
              ></span>
            </RouterLink>

            <!-- CTA Button -->
            <RouterLink to="/contact"
              class="ml-2 lg:ml-4 px-4 lg:px-6 py-2 md:py-2.5 font-Rubik font-bold text-xs lg:text-sm uppercase tracking-wider text-navyBlue bg-yellowMain rounded-full shadow-md hover:shadow-lg hover:-translate-y-0.5 transition-all duration-300 border-2 border-transparent hover:border-navyBlue">
              Kontakt
            </RouterLink>
          </div>
          
          <!-- Hamburger Icon -->
          <button 
            @click="toggleMenu"
            class="block md:hidden focus:outline-none z-[110] relative w-8 h-8 hamburger"
            :class="{ 'open': isMenuOpen }"
          >
            <span class="hamburger-top bg-navyBlue"></span>
            <span class="hamburger-middle bg-navyBlue"></span>
            <span class="hamburger-bottom bg-navyBlue"></span>
          </button>
        </div>
      </div>
    </nav>

    <!-- Mobile Menu Overlay -->
    <div class="md:hidden">
      <!-- Background Overlay (Dimmer) -->
      <div 
        v-if="isMenuOpen" 
        @click="closeMenu"
        class="fixed inset-0 bg-navyBlue/60 backdrop-blur-sm z-[105] transition-opacity duration-300"
      ></div>

      <!-- Drawer Menu -->
      <Transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="transform translate-x-full"
        enter-to-class="transform translate-x-0"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="transform translate-x-0"
        leave-to-class="transform translate-x-full"
      >
        <div 
          v-if="isMenuOpen"
          class="fixed top-0 right-0 h-dvh w-[85%] max-w-sm bg-white shadow-[-10px_0_30px_rgba(0,0,0,0.1)] z-[108] p-8 flex flex-col pt-20 overflow-y-auto"
        >
          <!-- Menu Content -->
          <div class="flex flex-col space-y-3">
            <p class="text-xs text-gray-400 uppercase tracking-[0.3em] font-bold mb-2">Nawigacja</p>
            <RouterLink 
              v-for="link in [
                { path: '/', label: 'Główna', icon: 'pi-home' },
                { path: '/offer', label: 'Oferta', icon: 'pi-briefcase' },
                { path: '/about', label: 'O nas', icon: 'pi-info-circle' },
                { path: '/contact', label: 'Kontakt', icon: 'pi-envelope' }
              ]" 
              :key="link.path"
              :to="link.path" 
              @click="closeMenu" 
              class="text-lg font-bold uppercase flex items-center gap-4 p-3 rounded-2xl transition-all"
              :class="isActiveLink(link.path) ? 'bg-yellowMain text-navyBlue' : 'text-navyBlue hover:bg-gray-50'"
            >
              <div class="w-10 h-10 rounded-xl bg-gray-50 flex items-center justify-center">
                <i :class="['pi', link.icon, 'text-lg', isActiveLink(link.path) ? 'text-navyBlue' : 'text-yellowMain']"></i>
              </div>
              {{ link.label }}
            </RouterLink>
          </div>

          <!-- Bottom Contact Info -->
          <div class="mt-12 mb-6 border-t border-gray-100 pt-6 space-y-4">
            <p class="text-xs text-gray-400 uppercase tracking-widest font-bold">Kontakt bezpośredni</p>
            
            <a href="tel:+48603386856" class="flex items-center gap-4 text-navyBlue font-bold group">
              <div class="w-10 h-10 rounded-full bg-yellowMain/10 flex items-center justify-center">
                <i class="pi pi-phone text-yellowMain"></i>
              </div>
              <span class="text-lg">+48 603-386-856</span>
            </a>

            <div class="flex items-start gap-4 text-gray-600">
              <div class="w-10 h-10 rounded-full bg-gray-50 flex items-center justify-center flex-shrink-0">
                <i class="pi pi-map-marker text-gray-400"></i>
              </div>
              <p class="text-sm leading-relaxed">
                ul. Legionów Polskich 1/11<br>
                62-700 Turek
              </p>
            </div>
          </div>
        </div>
      </Transition>
    </div>
  </header>
  
  <!-- Spacer -->
  <div class="h-[88px] md:h-[144px]" :class="{ 'md:h-[104px]': isScrolled }"></div>
</template>

<style scoped>
/* Fix for hamburger positioning if main.css fails */
.hamburger span {
  display: block;
  position: absolute;
  height: 2px;
  width: 100%;
  border-radius: 9px;
  opacity: 1;
  left: 0;
  transform: rotate(0deg);
  transition: .25s ease-in-out;
}

.hamburger-top { top: 6px; }
.hamburger-middle { top: 14px; }
.hamburger-bottom { top: 22px; }

.open .hamburger-top {
  top: 14px;
  transform: rotate(135deg);
}
.open .hamburger-middle {
  opacity: 0;
  left: -60px;
}
.open .hamburger-bottom {
  top: 14px;
  transform: rotate(-135deg);
}
</style>
