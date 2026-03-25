<template>
  <section id="booking" class="bg-white">
    <div class="section-container">
      <div class="text-center mb-16">
        <h2 class="heading-xl text-gray-900 mb-4">
          Book Your <span class="text-accent-600">Free Consultation</span>
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Ready to start your transformation? Schedule your free consultation and let's discuss your goals.
        </p>
      </div>

      <div class="max-w-4xl mx-auto">
        <div class="bg-gradient-to-br from-gray-50 to-white rounded-2xl shadow-2xl p-8 md:p-12">
          <form @submit.prevent="handleSubmit" class="space-y-6">
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div>
                <label for="name" class="block text-sm font-semibold text-gray-700 mb-2">
                  Full Name *
                </label>
                <input
                  id="name"
                  v-model="formData.name"
                  type="text"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                  placeholder="John Doe"
                />
              </div>

              <div>
                <label for="email" class="block text-sm font-semibold text-gray-700 mb-2">
                  Email Address *
                </label>
                <input
                  id="email"
                  v-model="formData.email"
                  type="email"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                  placeholder="john@example.com"
                />
              </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div>
                <label for="phone" class="block text-sm font-semibold text-gray-700 mb-2">
                  Phone Number
                </label>
                <input
                  id="phone"
                  v-model="formData.phone"
                  type="tel"
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                  placeholder="(555) 123-4567"
                />
              </div>

              <div>
                <label for="program" class="block text-sm font-semibold text-gray-700 mb-2">
                  Interested Program
                </label>
                <select
                  id="program"
                  v-model="formData.program"
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                >
                  <option value="">Select a program</option>
                  <option value="Personal Training">Personal Training</option>
                  <option value="Group Fitness">Group Fitness</option>
                  <option value="Online Coaching">Online Coaching</option>
                  <option value="Athletic Performance">Athletic Performance</option>
                </select>
              </div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div>
                <label for="date" class="block text-sm font-semibold text-gray-700 mb-2">
                  Preferred Date *
                </label>
                <input
                  id="date"
                  v-model="formData.preferredDate"
                  type="date"
                  required
                  :min="minDate"
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                />
              </div>

              <div>
                <label for="time" class="block text-sm font-semibold text-gray-700 mb-2">
                  Preferred Time *
                </label>
                <select
                  id="time"
                  v-model="formData.preferredTime"
                  required
                  class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                >
                  <option value="">Select a time</option>
                  <option value="6:00 AM - 8:00 AM">6:00 AM - 8:00 AM</option>
                  <option value="8:00 AM - 10:00 AM">8:00 AM - 10:00 AM</option>
                  <option value="10:00 AM - 12:00 PM">10:00 AM - 12:00 PM</option>
                  <option value="12:00 PM - 2:00 PM">12:00 PM - 2:00 PM</option>
                  <option value="2:00 PM - 4:00 PM">2:00 PM - 4:00 PM</option>
                  <option value="4:00 PM - 6:00 PM">4:00 PM - 6:00 PM</option>
                  <option value="6:00 PM - 8:00 PM">6:00 PM - 8:00 PM</option>
                </select>
              </div>
            </div>

            <div>
              <label for="message" class="block text-sm font-semibold text-gray-700 mb-2">
                Tell us about your goals
              </label>
              <textarea
                id="message"
                v-model="formData.message"
                rows="4"
                class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-accent-500 focus:border-accent-500 transition"
                placeholder="Share your fitness goals, experience level, and any specific needs..."
              ></textarea>
            </div>

            <div v-if="successMessage" class="bg-green-50 border border-green-200 text-green-700 px-4 py-3 rounded-lg">
              {{ successMessage }}
            </div>

            <button
              type="submit"
              :disabled="submitting"
              class="w-full btn-primary disabled:opacity-50 disabled:cursor-not-allowed"
            >
              {{ submitting ? 'Submitting...' : 'Book Free Consultation' }}
            </button>
          </form>
        </div>

        <div class="mt-12 grid grid-cols-1 md:grid-cols-3 gap-6 text-center">
          <div class="bg-white p-6 rounded-xl shadow-md">
            <div class="text-accent-600 mb-3">
              <svg class="w-10 h-10 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="font-bold text-gray-900 mb-2">Flexible Hours</h3>
            <p class="text-gray-600 text-sm">Available 6 AM - 8 PM</p>
          </div>

          <div class="bg-white p-6 rounded-xl shadow-md">
            <div class="text-accent-600 mb-3">
              <svg class="w-10 h-10 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
            </div>
            <h3 class="font-bold text-gray-900 mb-2">Multiple Locations</h3>
            <p class="text-gray-600 text-sm">Downtown & Online</p>
          </div>

          <div class="bg-white p-6 rounded-xl shadow-md">
            <div class="text-accent-600 mb-3">
              <svg class="w-10 h-10 mx-auto" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
            </div>
            <h3 class="font-bold text-gray-900 mb-2">Free Consultation</h3>
            <p class="text-gray-600 text-sm">No commitment required</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed } from 'vue'

const formData = ref({
  name: '',
  email: '',
  phone: '',
  program: '',
  preferredDate: '',
  preferredTime: '',
  message: ''
})

const submitting = ref(false)
const successMessage = ref('')

const minDate = computed(() => {
  const today = new Date()
  return today.toISOString().split('T')[0]
})

const handleSubmit = () => {
  submitting.value = true

  setTimeout(() => {
    successMessage.value = 'Booking submitted successfully! We will contact you soon to confirm your consultation.'

    formData.value = {
      name: '',
      email: '',
      phone: '',
      program: '',
      preferredDate: '',
      preferredTime: '',
      message: ''
    }

    submitting.value = false

    setTimeout(() => {
      successMessage.value = ''
    }, 5000)
  }, 1000)
}
</script>
