<template>
  <section id="blog" class="bg-gray-50">
    <div class="section-container">
      <div class="text-center mb-16">
        <h2 class="heading-xl text-gray-900 mb-4">
          Fitness <span class="text-accent-600">Tips & Articles</span>
        </h2>
        <p class="text-xl text-gray-600 max-w-3xl mx-auto">
          Expert advice, workout tips, and nutrition guidance to support your fitness journey.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div
          v-for="post in blogPosts"
          :key="post.id"
          class="bg-white rounded-2xl shadow-lg overflow-hidden card-hover cursor-pointer"
        >
          <div class="relative h-48 overflow-hidden">
            <img
              :src="post.imageUrl"
              :alt="post.title"
              class="w-full h-full object-cover transform hover:scale-110 transition-transform duration-500"
            />
          </div>

          <div class="p-6">
            <div class="flex items-center text-sm text-gray-500 mb-3">
              <svg class="w-4 h-4 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z" />
              </svg>
              {{ post.date }}
            </div>

            <h3 class="text-xl font-bold text-gray-900 mb-3 hover:text-accent-600 transition">
              {{ post.title }}
            </h3>

            <p class="text-gray-600 mb-4 leading-relaxed">
              {{ post.excerpt }}
            </p>

            <div class="flex items-center justify-between">
              <span class="text-sm text-gray-500">By {{ post.author }}</span>
              <button class="text-accent-600 font-semibold hover:text-accent-700 transition flex items-center">
                Read More
                <svg class="w-4 h-4 ml-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const blogPosts = [
  {
    id: 1,
    title: '5 Essential Exercises for Building Core Strength',
    excerpt: 'Discover the most effective exercises to build a strong, stable core that will improve your overall fitness and daily life.',
    imageUrl: 'https://images.pexels.com/photos/4162491/pexels-photo-4162491.jpeg?auto=compress&cs=tinysrgb&w=800',
    author: 'Coach Alex',
    date: 'March 15, 2026'
  },
  {
    id: 2,
    title: 'The Ultimate Guide to Pre and Post Workout Nutrition',
    excerpt: 'Learn how to fuel your body before and after workouts to maximize performance and recovery.',
    imageUrl: 'https://images.pexels.com/photos/1640777/pexels-photo-1640777.jpeg?auto=compress&cs=tinysrgb&w=800',
    author: 'Coach Alex',
    date: 'March 10, 2026'
  },
  {
    id: 3,
    title: 'How to Stay Motivated on Your Fitness Journey',
    excerpt: 'Practical tips and strategies to maintain motivation and consistency in your fitness routine.',
    imageUrl: 'https://images.pexels.com/photos/4162449/pexels-photo-4162449.jpeg?auto=compress&cs=tinysrgb&w=800',
    author: 'Coach Alex',
    date: 'March 5, 2026'
  }
]
</script>
