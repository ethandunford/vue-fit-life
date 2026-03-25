<template>
  <section id="programs" class="bg-white">
    <div class="section-container">
      <div class="text-center mb-16">
        <h2 class="heading-xl text-gray-900 mb-4">
          Training <span class="text-accent-600">Programs</span>
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Choose from our range of personalized training programs designed to help you achieve your fitness goals.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div
          v-for="program in programs"
          :key="program.id"
          class="bg-white rounded-2xl shadow-lg overflow-hidden card-hover relative"
        >
          <div v-if="program.isPopular" class="absolute top-4 right-4 z-10">
            <span class="bg-accent-600 text-white px-4 py-2 rounded-full text-sm font-semibold shadow-lg">
              Most Popular
            </span>
          </div>

          <div class="relative h-64 overflow-hidden">
            <img
              :src="program.imageUrl"
              :alt="program.title"
              class="w-full h-full object-cover transform hover:scale-110 transition-transform duration-500"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/60 to-transparent"></div>
          </div>

          <div class="p-8">
            <div class="flex justify-between items-start mb-4">
              <h3 class="text-2xl font-bold text-gray-900">{{ program.title }}</h3>
              <div class="text-right">
                <div class="text-3xl font-bold text-accent-600">${{ program.price }}</div>
                <div class="text-sm text-gray-500">{{ program.duration }}</div>
              </div>
            </div>

            <p class="text-gray-600 mb-6 leading-relaxed">
              {{ program.description }}
            </p>

            <div class="space-y-3 mb-6">
              <div
                v-for="(feature, index) in program.features"
                :key="index"
                class="flex items-start"
              >
                <svg class="w-5 h-5 text-accent-600 mr-3 flex-shrink-0 mt-0.5" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                </svg>
                <span class="text-gray-700">{{ feature }}</span>
              </div>
            </div>

            <button
              @click="scrollToBooking"
              class="w-full btn-primary"
            >
              Get Started
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const programs = [
  {
    id: 1,
    title: 'Personal Training',
    description: 'One-on-one personalized training sessions tailored to your specific goals and fitness level. Get dedicated attention and customized workout plans.',
    imageUrl: 'https://images.pexels.com/photos/416778/pexels-photo-416778.jpeg?auto=compress&cs=tinysrgb&w=800',
    duration: '12 weeks',
    price: 499.99,
    features: [
      'Personalized workout plans',
      'Nutritional guidance',
      'Progress tracking',
      '24/7 support'
    ],
    isPopular: true
  },
  {
    id: 2,
    title: 'Group Fitness',
    description: 'High-energy group training sessions that combine motivation, accountability, and community support to help you reach your goals.',
    imageUrl: 'https://images.pexels.com/photos/3757376/pexels-photo-3757376.jpeg?auto=compress&cs=tinysrgb&w=800',
    duration: '8 weeks',
    price: 299.99,
    features: [
      'Small group sessions',
      'Community support',
      'Varied workouts',
      'Flexible scheduling'
    ],
    isPopular: false
  },
  {
    id: 3,
    title: 'Online Coaching',
    description: 'Train from anywhere with custom workout plans, video demonstrations, and weekly check-ins. Perfect for busy schedules.',
    imageUrl: 'https://images.pexels.com/photos/4498606/pexels-photo-4498606.jpeg?auto=compress&cs=tinysrgb&w=800',
    duration: '16 weeks',
    price: 199.99,
    features: [
      'Custom workout videos',
      'Weekly video calls',
      'Meal planning',
      'Form review'
    ],
    isPopular: false
  },
  {
    id: 4,
    title: 'Athletic Performance',
    description: 'Advanced training program for athletes looking to enhance their performance, speed, agility, and overall athletic ability.',
    imageUrl: 'https://images.pexels.com/photos/1552242/pexels-photo-1552242.jpeg?auto=compress&cs=tinysrgb&w=800',
    duration: '12 weeks',
    price: 599.99,
    features: [
      'Sport-specific training',
      'Speed & agility work',
      'Injury prevention',
      'Performance testing'
    ],
    isPopular: true
  }
]

const scrollToBooking = () => {
  document.getElementById('booking')?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}
</script>
