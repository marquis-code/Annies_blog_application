<template>
  <div class="fixed w-full top-0 bg-gray-50">
    <header class="flex justify-between items-center max-w-6xl mx-auto px-5 pb-5 pt-3 lg:px-0">
        <nuxt-link to="/"><img src="/logo.png" class="rounded-full" /></nuxt-link>
        <ul class="md:flex items-center hidden space-x-4">
           <template v-for="(navItem, index) in nav">
               <li :key="index">
                  <nuxt-link class="ring-1 ring-gray-100 inline-block px-3 py-2 bg-gray-50 rounded-full text-sm font-medium hover:bg-gray-500 transition-all duration-300" :to="navItem.link">{{navItem.name}}</nuxt-link>
               </li>
           </template>
        </ul>
        <nuxt-link to="/auth/signin" class="px-5 py-2 text-sm bg-indigo-700 hover:bg-indigo-900 text-white rounded-full transition-all duration-500">Get started</nuxt-link>
    </header>
    <hr />
  </div>
</template>

<script>
  export default {
    name : 'HeaderSection',
    data(){
      return {
        nav : [
          {name : 'Our story', link : '/'},
          {name : 'Write', link : '/#'},
          {name : 'Sign in', link : '/auth/signin'},
          {name : 'About', link : '/#'}
        ]
      }
    }
  }
</script>
