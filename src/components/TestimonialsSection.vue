<template>
  <section id="testimonials" class="bg-gray-50">
    <div class="section-container">
      <div class="text-center mb-16">
        <h2 class="heading-xl text-gray-900 mb-4">
          Client <span class="text-accent-600">Success Stories</span>
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Real transformations from real people. See what our clients have achieved.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
        <div
          v-for="testimonial in testimonials"
          :key="testimonial.id"
          class="bg-white rounded-2xl shadow-lg p-8 card-hover"
        >
          <div class="flex items-start mb-6">
            <img
              :src="testimonial.clientImage"
              :alt="testimonial.clientName"
              class="w-20 h-20 rounded-full object-cover mr-6 ring-4 ring-accent-100"
            />
            <div class="flex-1">
              <h3 class="text-xl font-bold text-gray-900 mb-1">{{ testimonial.clientName }}</h3>
              <p class="text-accent-600 font-semibold mb-2">{{ testimonial.achievement }}</p>
              <div class="flex">
                <svg
                  v-for="i in 5"
                  :key="i"
                  class="w-5 h-5"
                  :class="i <= testimonial.rating ? 'text-yellow-400' : 'text-gray-300'"
                  fill="currentColor"
                  viewBox="0 0 20 20"
                >
                  <path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z" />
                </svg>
              </div>
            </div>
          </div>

          <div class="relative">
            <svg class="absolute top-0 left-0 w-8 h-8 text-accent-200 -mt-2 -ml-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" />
            </svg>
            <p class="text-gray-700 italic leading-relaxed pl-6">
              {{ testimonial.quote }}
            </p>
          </div>
        </div>
      </div>

      <div class="mt-16 bg-gradient-to-r from-accent-600 to-accent-700 rounded-2xl p-12 text-center shadow-2xl">
        <h3 class="text-3xl font-bold text-white mb-4">Ready to Write Your Success Story?</h3>
        <p class="text-xl text-accent-100 mb-8 max-w-2xl mx-auto">
          Join hundreds of satisfied clients who have transformed their lives with personalized training.
        </p>
        <button @click="scrollToBooking" class="bg-white text-accent-600 hover:bg-gray-100 font-semibold px-8 py-4 rounded-lg transition-all duration-300 transform hover:scale-105 shadow-lg">
          Start Your Transformation
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const testimonials = [
  {
    id: 1,
    clientName: 'Sarah Martinez',
    clientImage: 'https://images.pexels.com/photos/3768894/pexels-photo-3768894.jpeg?auto=compress&cs=tinysrgb&w=400',
    quote: 'Working with Coach Alex completely transformed my life. I lost 35 pounds and gained so much confidence. The personalized approach made all the difference!',
    achievement: 'Lost 35 lbs in 4 months',
    rating: 5
  },
  {
    id: 2,
    clientName: 'Michael Chen',
    clientImage: 'https://images.pexels.com/photos/5384445/pexels-photo-5384445.jpeg?auto=compress&cs=tinysrgb&w=400',
    quote: 'I have tried many trainers before, but none compare to the dedication and expertise I found here. My strength has doubled and I feel amazing!',
    achievement: 'Doubled strength gains',
    rating: 5
  },
  {
    id: 3,
    clientName: 'Jessica Thompson',
    clientImage: 'https://images.pexels.com/photos/4662353/pexels-photo-4662353.jpeg?auto=compress&cs=tinysrgb&w=400',
    quote: 'The online coaching program fit perfectly into my busy schedule. I never thought I could get such great results training from home!',
    achievement: 'Achieved dream body',
    rating: 5
  },
  {
    id: 4,
    clientName: 'David Rodriguez',
    clientImage: 'https://images.pexels.com/photos/5384630/pexels-photo-5384630.jpeg?auto=compress&cs=tinysrgb&w=400',
    quote: 'As an athlete, I needed specialized training to take my performance to the next level. This program delivered beyond my expectations!',
    achievement: 'Improved performance 40%',
    rating: 5
  }
]

const scrollToBooking = () => {
  document.getElementById('booking')?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}
</script>
