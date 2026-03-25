<template>
  <section id="home" class="relative h-screen flex items-center justify-center overflow-hidden">
    <div class="absolute inset-0 z-0">
      <img
        src="https://images.pexels.com/photos/1552242/pexels-photo-1552242.jpeg"
        alt="Fitness training"
        class="w-full h-full object-cover"
      />
      <div class="absolute inset-0 bg-gradient-to-r from-black/70 via-black/50 to-transparent"></div>
    </div>

    <div class="relative z-10 section-container text-left max-w-4xl">
      <div class="animate-fade-in">
        <h1 class="heading-display text-white mb-6">
          Transform Your Body,<br />
          <span class="text-accent-500">Transform Your Life</span>
        </h1>
        <p class="text-xl md:text-2xl text-gray-200 mb-8 max-w-2xl leading-relaxed">
          Achieve your fitness goals with personalized training programs designed for real results. Your journey to a stronger, healthier you starts here.
        </p>
        <div class="flex flex-col sm:flex-row gap-4">
          <button @click="scrollToPrograms" class="btn-primary">
            Explore Programs
          </button>
          <button @click="scrollToBooking" class="btn-secondary">
            Book Free Consultation
          </button>
        </div>
      </div>

      <div class="mt-16 grid grid-cols-1 sm:grid-cols-3 gap-8">
        <div class="text-center sm:text-left">
          <div class="text-4xl md:text-5xl font-bold text-white mb-2">500+</div>
          <div class="text-gray-300">Clients Transformed</div>
        </div>
        <div class="text-center sm:text-left">
          <div class="text-4xl md:text-5xl font-bold text-white mb-2">10+</div>
          <div class="text-gray-300">Years Experience</div>
        </div>
        <div class="text-center sm:text-left">
          <div class="text-4xl md:text-5xl font-bold text-white mb-2">4.9</div>
          <div class="text-gray-300">Average Rating</div>
        </div>
      </div>
    </div>

    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 z-10 animate-bounce">
      <button @click="scrollDown" class="text-white" aria-label="Scroll down">
        <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
      </button>
    </div>
  </section>
</template>

<script setup lang="ts">
const scrollToPrograms = () => {
  document.getElementById('programs')?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

const scrollToBooking = () => {
  document.getElementById('booking')?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

const scrollDown = () => {
  window.scrollBy({ top: window.innerHeight, behavior: 'smooth' })
}
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out;
}
</style>
