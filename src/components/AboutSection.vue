<template>
  <section id="about" class="bg-gray-50">
    <div class="section-container">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
        <div class="order-2 lg:order-1">
          <h2 class="heading-xl text-gray-900 mb-6">
            Meet Your <span class="text-accent-600">Coach</span>
          </h2>
          <p class="text-lg text-gray-700 mb-6 leading-relaxed">
            Hi, I'm Alex Rivera, a certified personal trainer with over 10 years of experience helping people transform their lives through fitness. My journey started when I overcame my own health challenges, and now I'm passionate about empowering others to achieve their goals.
          </p>
          <p class="text-lg text-gray-700 mb-8 leading-relaxed">
            I believe fitness is not just about physical transformation—it's about building confidence, discipline, and a sustainable lifestyle. Every client is unique, which is why I create personalized programs tailored to your specific needs, goals, and lifestyle.
          </p>

          <div class="mb-8">
            <h3 class="text-xl font-bold text-gray-900 mb-4">Certifications & Credentials</h3>
            <ul class="space-y-3">
              <li v-for="cert in certifications" :key="cert" class="flex items-start">
                <svg class="w-6 h-6 text-accent-600 mr-3 flex-shrink-0 mt-0.5" fill="currentColor" viewBox="0 0 20 20">
                  <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd" />
                </svg>
                <span class="text-gray-700">{{ cert }}</span>
              </li>
            </ul>
          </div>

          <div>
            <h3 class="text-xl font-bold text-gray-900 mb-4">Training Philosophy</h3>
            <p class="text-gray-700 leading-relaxed">
              "Success in fitness comes from consistency, not perfection. I'm here to guide you, support you, and celebrate every milestone along the way. Together, we'll build a sustainable approach that fits your life."
            </p>
          </div>
        </div>

        <div class="order-1 lg:order-2">
          <div class="relative">
            <div class="absolute inset-0 bg-accent-600 rounded-2xl transform rotate-6"></div>
            <img
              src="https://images.pexels.com/photos/3490348/pexels-photo-3490348.jpeg?auto=compress&cs=tinysrgb&w=800"
              alt="Coach Alex Rivera"
              class="relative rounded-2xl shadow-2xl w-full aspect-[4/5] object-cover"
              loading="lazy"
            />
          </div>

          <div class="mt-8 grid grid-cols-2 gap-4">
            <div class="bg-white p-6 rounded-xl shadow-md text-center">
              <div class="text-3xl font-bold text-accent-600 mb-2">500+</div>
              <div class="text-gray-600">Success Stories</div>
            </div>
            <div class="bg-white p-6 rounded-xl shadow-md text-center">
              <div class="text-3xl font-bold text-accent-600 mb-2">15K+</div>
              <div class="text-gray-600">Training Hours</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const certifications = [
  'NASM Certified Personal Trainer (CPT)',
  'ACE Fitness Nutrition Specialist',
  'Precision Nutrition Level 1 Certified',
  'CrossFit Level 2 Trainer',
  'TRX Suspension Training Certified',
  'First Aid & CPR Certified'
]
</script>
