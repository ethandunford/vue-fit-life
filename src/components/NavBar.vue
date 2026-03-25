<template>
  <nav :class="['fixed w-full z-50 transition-all duration-300', scrolled ? 'bg-white shadow-lg' : 'bg-transparent']">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-20">
        <div class="flex-shrink-0">
          <a href="#home" @click.prevent="scrollToSection('home')" class="text-2xl font-display font-bold">
            <span :class="scrolled ? 'text-gray-900' : 'text-white'">FIT</span>
            <span class="text-accent-600">LIFE</span>
          </a>
        </div>

        <div class="hidden md:flex items-center space-x-8">
          <a
            v-for="item in navItems"
            :key="item.id"
            :href="`#${item.id}`"
            @click.prevent="scrollToSection(item.id)"
            :class="[
              'font-medium transition-colors duration-200',
              scrolled ? 'text-gray-700 hover:text-accent-600' : 'text-white hover:text-accent-400'
            ]"
          >
            {{ item.label }}
          </a>
          <button
            @click="scrollToSection('booking')"
            class="btn-primary !py-3 !px-6"
          >
            Book Now
          </button>
        </div>

        <div class="md:hidden">
          <button
            @click="mobileMenuOpen = !mobileMenuOpen"
            :class="['p-2 rounded-md', scrolled ? 'text-gray-700' : 'text-white']"
            aria-label="Toggle menu"
          >
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path
                v-if="!mobileMenuOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <div
      v-if="mobileMenuOpen"
      class="md:hidden bg-white border-t border-gray-200"
    >
      <div class="px-4 pt-2 pb-4 space-y-1">
        <a
          v-for="item in navItems"
          :key="item.id"
          :href="`#${item.id}`"
          @click.prevent="scrollToSection(item.id); mobileMenuOpen = false"
          class="block px-3 py-2 text-gray-700 hover:text-accent-600 hover:bg-gray-50 rounded-md font-medium"
        >
          {{ item.label }}
        </a>
        <button
          @click="scrollToSection('booking'); mobileMenuOpen = false"
          class="w-full mt-4 btn-primary"
        >
          Book Now
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const scrolled = ref(false)
const mobileMenuOpen = ref(false)

const navItems = [
  { id: 'home', label: 'Home' },
  { id: 'about', label: 'About' },
  { id: 'programs', label: 'Programs' },
  { id: 'testimonials', label: 'Testimonials' },
  { id: 'blog', label: 'Blog' },
  { id: 'contact', label: 'Contact' }
]

const scrollToSection = (id: string) => {
  const element = document.getElementById(id)
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top
    const offsetPosition = elementPosition + window.pageYOffset - offset

    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
  }
}

const handleScroll = () => {
  scrolled.value = window.scrollY > 20
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
