<template>
  <div class="max-w-6xl mx-auto mt-28">
    <form
      @submit.prevent="handleSubmit"
      class="rounded  md:ring-1 ring-gray-200 shadow-sm space-y-6 w-11/12 md:mb-0 pb-3 mb-10 px-2 sm:w-10/12 lg:w-6/12 mx-auto md:p-6"
    >
       <div class="flex flex-col items-center">
      <img src="/logo.png" class="rounded-full" />
      <h1 class="font-sans text-xl font-medium">Sign up</h1>
    </div>
      <div class="md:flex justify-between items-center md:space-x-6 space-y-6 md:space-y-0">
        <div class="space-y-3">
          <label class="select-none">First Name*</label>
          <input
            class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
            v-model="formData.firstName"
            placeholder="Enter First Name"
            type="text"
          />
        </div>
        <div class="space-y-3">
          <label class="select-none">Last Name*</label>
          <input
            class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
            v-model="formData.lastName"
            placeholder="Enter Last Name"
            type="text"
          />
        </div>
      </div>
      <div class="space-y-3">
        <label class="select-none">Email Address*</label>
        <input
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          v-model="formData.emailAddress"
          placeholder="Enter Email Address"
          type="email"
        />
      </div>
      <div class="space-y-3">
        <label class="select-none">Your Industry*</label>
        <select
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          v-model="formData.industry"
        >
         <option disabled value="">Select Your Industry</option>
          <option value="medicine">Medicine</option>
          <option value="finance">Finance</option>
          <option value="technology">Technology</option>
        </select>
      </div>
      <div class="space-y-3">
        <label class="select-none">Password*</label>
        <input
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          v-model="formData.password"
          placeholder="Enter Password"
          type="password"
        />
      </div>
      <div>
        <button class="bg-indigo-700 w-full text-white font-sans rounded shadow-sm py-2">Continue</button>
      </div>
      <div class="flex justify-center items-center">
          <span class="font-sans text-sm text-gray-600 select-none font-medium">Already have an account ? <nuxt-link class="hover:underline hover:text-green-500 cursor-pointer select-none" to="/auth/signin">Sign in</nuxt-link></span>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        firstName: "",
        lastName: "",
        emailAddress: "",
        password: "",
        industry: "",
      },
    };
  },
  methods: {
    resetInputFields(){
        this.formData.firstName = ""
        this.formData.lastName = "",
        this.formData.emailAddress = "",
        this.formData.password = "",
        this.formData.industry = ""
    },
    handleSubmit() {
      // https://annie-blog.herokuapp.com/
        console.log(this.formData)
        this.resetInputFields();
    },
  },
};
</script>
