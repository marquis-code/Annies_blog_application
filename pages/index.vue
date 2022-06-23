<template>
  <div>
    <div class="relative min-h-full container mx-auto">
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
    <!-- <div class="md:flex md:px-5 justify-between container mx-auto">
      <section class="lg:w-7/12 md:w-1/2 md:p-2 p-4 lg:px-0">
        <div
          v-for="post in posts"
          :key="post"
          class="sm:flex items-center lg:space-x-4 overflow-y-auto"
        >
          <div class="space-y-2 my-5">
            <div class="flex items-center space-x-3">
              <img
                :src="post.image"
                alt="author-profile-pic"
                class="lg:h-10 lg:w-10 w-8 h-8 rounded-full"
              />
              <p class="text-gray-500 font-sans text-sm lg:text-base select-none">
                {{ post.author }}
              </p>
            </div>
            <h1 class="font-sans font-bold lg:text-2xl text-lg">
              {{
                post.title.length > 30
                  ? `${post.title.slice(0, 50)}...`
                  : post.title
              }}
            </h1>
            <p class="text-gray-400 font-sans lg:text-base text-xs select-none">
              {{
                post.description.length > 50
                  ? `${post.description.slice(0, 80)}...`
                  : post.description
              }}
            </p>
            <div class="flex items-center space-x-3">
              <p class="text-xs font-sans font-lighter text-gray-400 select-none">
                {{ post.date }}
              </p>
              <p class="text-xs font-sans font-lighter text-gray-400 select-none">
                {{ post.readingTime }} mins read
              </p>
              <div v-for="hashTag in post.hashTags" :key="hashTag">
                <span
                  class="text-xs font-sans font-lighter text-gray-500 bg-gray-300 rounded-full py-2 px-3 lg:p-3 select-none"
                  >{{ hashTag }}</span
                >
              </div>
            </div>
             <div class="flex justify-center items-center pt-3">
            <img
              :src="post.image"
              alt="post-image"
              class="h-full w-full object-contain"
            />
          </div>
          </div> 
        </div>
      </section>
      <section class="lg:w-4/12 md:w-1/2 lg:mt-12 md:px-3 px-4 lg:px-0 lg:flex -z-0">
        <div class="">
          <div class="lg:sticky top-24 my-5">
            <h2
              class="uppercase font-medium font-sans text-xs sm:text-sm pb-1"
            >
              Discover more of what matters to you
            </h2>
            <div class="flex flex-wrap mb-2 p-2">
              <div
                v-for="category in categories"
                :key="category"
                class="mr-2 my-1"
              >
                <p
                  class="rounded-sm shadow p-2 ring-1 text-xs ring-gray-300 md:text-sm text-gray-400 select-none cursor-pointer"
                >
                  {{ category }}
                </p>
              </div>
               <div class="mt-3">
                    <carousel
                :centerMode="true"
                :loop="true"
                :perPage="1"
                :autoplay="true"
                :paginationEnabled="false"
              >
                <slide v-for="singleImage in imagesList" :key="singleImage">
                  <img
                    :src="singleImage.imageSrc"
                    class="object-cover rounded shadow-sm h-1/2 w-full mb-2"
                  />
                  <nuxt-link class="" to="">{{
                    singleImage.imageDescription.length > 10
                      ? `${singleImage.imageDescription.slice(0, 60)}...`
                      : singleImage.imageDescription
                  }}</nuxt-link>
                  <div class="">
                    <button
                      class="ring-1 ring-gray-100 hover:bg-indigo-700 rounded-full mt-1 shadow-sm text-white font-medium text-sm bg-indigo-500 py-1 px-4"
                    >
                      Read more
                    </button>
                  </div>
                </slide>
              </carousel>
               </div>
            </div> 
          </div>
        </div> 
      </section>
    </div> -->
    <FooterSection />
  </div>
</template>

<script>
export default {
  async asyncData({$axios}){
    const allPosts = await $axios.$get('https://annie-blog.herokuapp.com/api/post/')
    console.log(allPosts)
  }
}
</script>

//  <script>
// import { Carousel, Slide } from "vue-carousel";
// export default {
//   components: {
//     Carousel,
//     Slide,
//   },
//   data() {
//     return {
//       imagesList: [
//         {
//           imageSrc: "/home7.jpeg",
//           imageDescription:
//             "Myths about vue js and things people dont know about Vue js",
//         },
//         {
//           imageSrc: "/code1.jpg",
//           imageDescription: "Coding is fun with Marquis",
//         },
//         {
//           imageSrc: "/code2.jpg",
//           imageDescription: "Coding is fun with marquis",
//         },
//         { imageSrc: "/code3.jpg", imageDescription: "Nothing here to see" },
//       ],
//       categories: [
//         "Self",
//         "Relationship",
//         "Data Science",
//         "Programming",
//         "Productivity",
//         "Javascript",
//         "Machine Learning",
//         "Politics",
//         "Health",
//       ],
//       posts: [
//         {
//           title: "Top 10 Algorithms to improve your javascript skills",
//           author: "Hunter Walk",
//           description:
//             "1. Find the missing number in the array input: [1,2,3,4,5,6,7,9,10] output: 5 const find_missing = function(input)",
//           hashTags: ["Technology"],
//           readingTime: "4",
//           date: "june 10",
//           image: "/home4.jpg",
//         },
//         {
//           title: "A Primer on Monkeypox",
//           author: "Brandy L Schillace",
//           description:
//             "Reviewing medical history to forecast future disease-Headlines began appearing last month:monkeypox, a zoonotic(usually occuring in animals)",
//           hashTags: ["health"],
//           readingTime: "5",
//           date: "May 31",
//           image: "/home5.jpeg",
//         },
//         {
//           title: "The Last Movie Star - Tom Cruise",
//           author: "David paul",
//           description:
//             "Forget the other three wives, Tom married Tom-Tigger alert: aggressive language ned tanen, the president of paramount pictures movie group",
//           hashTags: ["movies"],
//           readingTime: "25",
//           date: "DFecember 31",
//           image: "/home6.jpeg",
//         },
//         {
//           title: "Period Tracking, Abortions, and Privacy",
//           author: "caroline sinders",
//           description:
//             "Our reproductive freedom and our devices are at risk-The last few weeks have been incredibly demoralizing, draining and upsetting",
//           hashTags: ["Roe V Wade"],
//           readingTime: "5",
//           date: "september 31",
//           image: "/home7.jpeg",
//         },
//          {
//           title: "What does a perfect work day look like?",
//           author: "Dr. Tiffany",
//           description:
//             "My 20-years expriement with work/life balance is paying off-The meditation teacherin me wishes this article was about manifesting the perfect day",
//           hashTags: ["Pleasure Activism"],
//           readingTime: "5",
//           date: "september 31",
//           image: "/home4.jpg",
//         },
//         {
//           title: "How Environmental Racism Became a Silent Killer in Black Communities",
//           author: "Allison Gaines",
//           description:
//             "you think Black people are just blowing smoke when we say racism is everywhere, you’d be sadly mistaken. Environmental racism is a silent killer: policies, regulations, and corporate decisions often target Black, and minority communities for “locally undesirable land uses,” exposing them to “toxic and hazardous waste.",
//           hashTags: ["Racis"],
//           readingTime: "13",
//           date: "june 6",
//           image: "/home7.jpeg",
//         }
//       ],
//     };
//   },
// };
// </script>
