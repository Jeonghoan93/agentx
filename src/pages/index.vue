<script setup lang="ts">
// No additional logic needed for static hero section
</script>

<template>
  <Navbar />

  <v-container class="bg-gray-6 mt-[60px] flex flex-col gap-10 py-10">
    <section class="bg-gray-6 mt-[60px] py-10">
      <div
        class="container mx-auto flex flex-col-reverse md:flex-row items-center gap-12 px-4"
      >
        <!-- 2nd View: Image -->
        <div class="w-full md:w-1/2">
          <div class="relative overflow-hidden rounded-xl shadow-lg">
            <!-- gradient overlay -->
            <div
              class="absolute inset-0 bg-gradient-to-tr from-[#1c1c1e]/90 via-[#1c1c1e]/60 to-transparent pointer-events-none"
            ></div>

            <!-- the image itself -->
            <img
              src="/assets/images/office1.jpg"
              alt="AgentX Robotics and AI"
              class="object-cover w-full h-full"
            />
          </div>
        </div>

        <!-- 1st View: Title, Description, Buttons & Metrics -->
        <div class="w-full md:w-1/2 flex flex-col gap-6">
          <h1 class="text-4xl font-bold text-light-1 text-white">
            Your Everyday AI Partner
            <br />
            <span class="text-grey-50">For Retail Excellence</span>
          </h1>
          <p class="text-grey-lighten-3 text-base font-semiobld">
            Hire top-tier AI software engineers or partner with robotics
            providers to elevate your retail operations. Customize solutions
            that fit your business needs and drive innovation on the floor.
          </p>

          <!-- Action Buttons -->
          <div class="flex flex-wrap gap-4">
            <button
              class="px-6 py-3 rounded-lg bg-blue-darken-1 text-white transition hover:scale-105"
            >
              <span class="font-semibold"> See how we can help you </span>
            </button>
            <button
              class="px-6 py-3 rounded-lg bg-blue-darken-2 text-white hover:scale-105 transition"
            >
              <span class="font-semibold"> Rent Robotics</span>
            </button>
          </div>

          <!-- Metrics -->
          <div class="flex justify-between mt-6 text-cyan-lighten-4">
            <div class="flex flex-col items-start">
              <span class="text-3xl font-bold text-light-1">100+</span>
              <span class="text-light-2">Engineers Hired</span>
            </div>
            <div class="flex flex-col items-start">
              <span class="text-3xl font-bold text-light-1">50+</span>
              <span class="text-light-2">Retail Partners</span>
            </div>
            <div class="flex flex-col items-start">
              <span class="text-3xl font-bold text-light-1">200+</span>
              <span class="text-light-2">Robotic Units</span>
            </div>
          </div>
        </div>
      </div>
    </section>
  </v-container>
</template>

<style scoped>
/* ensures the overlay and image share the same rounding */
.relative img,
.relative .bg-gradient-to-tr {
  border-radius: 0.75rem; /* matches rounded-xl */
}
</style>
