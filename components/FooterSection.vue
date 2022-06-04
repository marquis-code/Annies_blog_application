<template>
   <footer class="bg-black p-5 flex justify-center items-center">
       <span class="font-sans font-medium select-none text-center text-white">copyright @ Annie's blog {{todaysDate}}</span>
   </footer>
</template>

<script>
export default {
  name: 'FooterComponent',
  computed: {
      todaysDate() {
        let date = new Date()
        return date.getFullYear()
      }
  }
}
</script>