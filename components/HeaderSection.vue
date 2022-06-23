<template>
  <div class="">
    <header class="flex justify-between items-center container mx-auto pb-5 pt-3 lg:px-0 fixed w-full top-0 bg-gray-50 px-3 z-20">
        <nuxt-link to="/"><img src="/logo.png" class="rounded-full" /></nuxt-link>
        <ul class="md:flex items-center hidden space-x-4">
           <template v-for="(navItem, index) in nav">
               <li :key="index">
                  <nuxt-link class="ring-1 ring-gray-100 inline-block px-3 py-2 bg-gray-50 rounded-full text-sm font-medium hover:bg-gray-500 transition-all duration-300" :to="navItem.link">{{navItem.name}}</nuxt-link>
               </li>
           </template>
        </ul>
        <button class="animate-bounce px-5 py-2 text-sm bg-indigo-700 hover:bg-indigo-900 text-white rounded-full transition-all duration-500 hidden md:flex"><nuxt-link to="#">Get started</nuxt-link></button> 

         <button class="px-3 py-2 rounded-sm shadow-sm bg-indigo-700 text-white transition-all duration-500 md:hidden" @click="handleDropdown"><font-awesome-icon :icon="['fa', 'bars']"  /></button> 
    </header>
    <hr />
     <div v-if="showDropdown" class="bg-indigo-800 p-5 fixed top-20 w-full h-screen z-10 container mx-auto md:hidden transition-all duration-500">
         <ul class="">
           <template v-for="(navItem, index) in nav">
               <li :key="index" class="my-3" @click="handleDropdown">
                  <nuxt-link class="ring-1 text-white w-full p-3 ring-gray-100 inline-block overflow-hidden  rounded-sm shadow-sm text-lg font-medium hover:bg-indigo-900 transition-all duration-300" :to="navItem.link">{{navItem.name}}</nuxt-link>
               </li>
           </template>
        </ul>
     </div>
  </div>
</template>

<script>
  export default {
    name : 'HeaderSection',
    data(){
      return {
        showDropdown : false,
        nav : [
          // {name : 'Our story', link : '/'},
          {name : 'Write', link : '/write'},
          {name : 'About', link : '/about'},
          {name : 'Sign in', link : '/auth/signin'},
        ]
      }
    },
    methods : {
      handleDropdown(){
        this.showDropdown = !this.showDropdown
      }
    }
  }
</script>
