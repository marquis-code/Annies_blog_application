<template>
  <div>
    <carousel :perPage="1" :autoPlay="true">
      <slide v-for="(image, index) in imageList" :key="index">
        <img
          :src="image"
          height="100%"
          class="object-cover h-full w-full absolute inset-0 -z-0"
          alt="Advanced home image"
        />
      </slide>
    </carousel>
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";
export default {
    name : 'ImageCarousel',
    components: { Carousel, Slide },
    data(){
        return {
       imageList: [
            "/home1.jpg",
            "/home2.jpg",
            "/home3.jpg",
            "/home4.jpg",
            "/home5.jpeg"
      ]
        }
    }
}
</script>
