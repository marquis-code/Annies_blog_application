<template>
  <div>
    <div class="relative min-h-full">
      <img
        src="/home8.jpg"
        alt="Advanced home image"
        class="object-cover h-full w-full absolute inset-0 -z-0"
      />
      <div
        class="inset-0 absolute bg-gradient-to-b from-white via-white/60 to-transparent"
      ></div>
      <div class="h-full relative">
        <HeaderSection />
        <MainSection />
      </div>
    </div>
    <div class="lg:flex md:px-5 justify-between max-w-7xl mx-auto">
      <section class="lg:w-7/12 md:p-2 p-4 lg:px-0">
        <div
          v-for="post in posts"
          :key="post"
          class="sm:flex items-center lg:space-x-4 overflow-y-auto"
        >
          <div class="space-y-3">
            <div class="flex items-center space-x-3">
              <img
                :src="post.image"
                alt="author-profile-pic"
                class="lg:h-10 lg:w-10 w-8 h-8 rounded-full"
              />
              <p class="text-gray-500 font-sans text-sm lg:text-base">
                {{ post.author }}
              </p>
            </div>
            <h1 class="font-sans font-bold lg:text-2xl text-xl">
              {{
                post.title.length > 30
                  ? `${post.title.slice(0, 50)}...`
                  : post.title
              }}
            </h1>
            <p class="text-gray-400 font-sans lg:text-base text-sm">
              {{
                post.description.length > 50
                  ? `${post.description.slice(0, 50)}...`
                  : post.description
              }}
            </p>
            <div class="flex items-center space-x-4">
              <p class="text-xs font-sans font-lighter text-gray-400">
                {{ post.date }}
              </p>
              <p class="text-xs font-sans font-lighter text-gray-400">
                {{ post.readingTime }} mins read
              </p>
              <div v-for="hashTag in post.hashTags" :key="hashTag">
                <span
                  class="text-xs font-sans font-lighter text-gray-500 bg-gray-300 rounded-full py-2 px-3 lg:p-3"
                  >{{ hashTag }}</span
                >
              </div>
            </div>
          </div>
          <div class="flex justify-center items-center">
            <img
              :src="post.image"
              alt="post-image"
              class="h-72 w-72 object-contain"
            />
          </div>
        </div>
      </section>
      <section class="lg:w-4/12 lg:mt-12 md:px-3 px-4 lg:px-0 lg:flex">
        <div class="">
          <div class="md:sticky top-24">
            <h2 class="uppercase font-medium font-sans text-xs md:text-base pb-1">
              Discover more of what matters to you
            </h2>
            <div class="flex flex-wrap mb-2">
              <div
                v-for="category in categories"
                :key="category"
                class="mr-2 my-1"
              >
                <p
                  class="rounded-sm shadow p-2 ring-1 text-xs ring-gray-300 md:text-sm text-gray-400"
                >
                  {{ category }}
                </p>
              </div>
            </div>
            <carousel :centerMode="true" :loop="true" :perPage="1" :autoplay="true" :paginationPosition="top-overlay" :paginationEnabled="false">
              <slide v-for="singleImage in imagesList" :key="singleImage">
                <img :src="singleImage.imageSrc" class="object-cover rounded shadow-sm h-1/2 w-full mb-2" />
                <nuxt-link class="" to="">{{singleImage.imageDescription.length > 10 ? `${singleImage.imageDescription.slice(0,50)}...` : singleImage.imageDescription}}</nuxt-link>
                <div class="">
                  <button class="ring-1 ring-gray-100 hover:bg-indigo-700 rounded-full mt-1 shadow-sm text-white font-medium text-sm bg-indigo-500 py-1 px-4">Read more</button>
                </div>
              </slide>
            </carousel>
          </div>
        </div>
      </section>
    </div>
    <FooterSection />
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";
export default {
  components: {
    Carousel,
    Slide,
  },
  data() {
    return {
      imagesList: [
        {imageSrc :  "/home7.jpeg", imageDescription : 'Myths about vue js and things people dont know about Vue js'},
        {imageSrc :  "/code1.jpg", imageDescription : 'Coding is fun with Marquis'},
        {imageSrc :  "/code2.jpg", imageDescription : 'Coding is fun with marquis'},
        {imageSrc :  "/code3.jpg", imageDescription : 'Nothing here to see'},
      ],
      categories: [
        "Self",
        "Relationship",
        "Data Science",
        "Programming",
        "Productivity",
        "Javascript",
        "Machine Learning",
        "Politics",
        "Health",
      ],
      posts: [
        {
          title: "15,000 Tech Workers Have Been Let Go In May. Were You..",
          author: "Hunter Walk",
          description:
            "The thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn",
          hashTags: ["Technology"],
          readingTime: "4",
          date: "May 31",
          image: "/home4.jpg",
        },
        {
          title: "15,000 Tech Workers Have Been Let Go In May. Were You..",
          author: "Hunter Walk",
          description:
            "The thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn",
          hashTags: ["Technology"],
          readingTime: "4",
          date: "May 31",
          image: "/home5.jpeg",
        },
        {
          title: "15,000 Tech Workers Have Been Let Go In May. Were You..",
          author: "Hunter Walk",
          description:
            "The thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn",
          hashTags: ["Technology"],
          readingTime: "4",
          date: "May 31",
          image: "/home6.jpeg",
        },
        {
          title: "15,000 Tech Workers Have Been Let Go In May. Were You..",
          author: "Hunter Walk",
          description:
            "The thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn",
          hashTags: ["Technology"],
          readingTime: "4",
          date: "May 31",
          image: "/home7.jpeg",
        },
        {
          title: "15,000 Tech Workers Have Been Let Go In May. Were You..",
          author: "Hunter Walk",
          description:
            "The thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn he thin gyou know when you loose your job is a Downturn",
          hashTags: ["Technology"],
          readingTime: "4",
          date: "May 31",
          image: "/home8.jpg",
        },
      ],
    };
  },
};
</script>
