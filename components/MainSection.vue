<template>
  <div>
    <main class="container mx-auto lg:px-0 pt-14 pb-10 lg:pt-12 mt-20">
      <h1
        class="select-none capitalize font-semibold text-4xl lg:text-7xl text-center leading-snug"
      >
        Welcome to <br /><span
          class="font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-indigo-600 via-pink-600 to-yellow-600"
          >Annie's Blog.</span
        >
      </h1>
      <p
        class="select-none mt-10 text-base sm:text-2xl text-center lg:text-3xl font-medium"
      >
        Read intresting stories, Explore and Learn from writers on any topic.
      </p>
      <div class="mt-10 lg:mt-14 flex justify-center items-center space-x-4">
        <nuxt-link
          to="#"
          class="px-10 py-3 text-sm bg-indigo-700 hover:bg-indigo-900 text-white rounded-full transition-all duration-500"
          >Start reading</nuxt-link
        >
      </div>
       <!-- <carousel :perPage="1" :autoPlay="true">
        <slide v-for="singleImage in imagesList" :key="singleImage">
            <img :src="singleImage" class="object-cover h-full w-full inset-0 -z-0" />
        </slide>
      </carousel> -->
    </main>
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";
export default {
    name : 'MainSection',
     components: {
        Carousel,
        Slide
    },
    data(){
        return {
       imagesList: [
          "/home7.jpeg",
          "/home6.jpeg",
          "/home5.jpeg",
      ]
        }
    }
}
</script>

