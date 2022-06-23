<template>
  <div class="max-w-6xl mx-auto mt-28">
    <form
      @submit.prevent="handleSubmit"
      class="rounded  md:ring-1 ring-gray-200 shadow-sm space-y-6 w-11/12 md:mb-0 pb-3 mb-10 px-2 sm:w-10/12 lg:w-6/12 mx-auto md:p-6"
    >
       <div class="flex flex-col items-center">
      <img src="/logo.png" class="rounded-full" />
      <h1 class="font-sans text-xl font-medium">New Blog Post</h1>
    </div>
      
        <div class="space-y-3">
          <label class="select-none font-medium">Blog Title*</label>
          <input
            class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
            v-model="formData.blogTitle"
            placeholder="Enter Blog Title"
            type="text"
          />
        </div>
        <div class="space-y-3">
          <label class="select-none font-medium">Blog Subtitle*</label>
          <input
            class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
            v-model="formData.blogSubtitle"
            placeholder="Enter Blog subtitle"
            type="text"
          />
        </div>
     
      <div class="space-y-3">
        <label class="select-none font-medium">Blog Hash Tags*</label>
        <p className='text-xs text-gray-400 font-sans font-thin'>Ensure every tag starts with # and ensure you add a comma after every hash tag and space after every hash tag example: <span className='text-gray-300'>#health, #finance, #movies</span></p>
        <input
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          v-model="formData.hashTags"
          placeholder="Enter Blog hash tags"
          type="text"
        />
      </div>
        <div class="space-y-3">
        <label class="select-none font-medium">Blog Featured Image*</label>
        <input
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          type="file"
        />
      </div>
      <div class="space-y-3">
        <label class="select-none font-medium">Blog Reading Time*</label>
        <input
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          v-model="formData.readingTime"
          placeholder="Select blog reading time"
          type="number"
        />
      </div>
      <div class="space-y-3">
        <label class="select-none font-medium">Blog Description*</label>
        <textarea
          class="w-full py-2 rounded shadow-sm outline-none px-3 ring-1 ring-gray-100 focus:ring-green-500 transition-all duration-500"
          v-model="formData.description"
          placeholder="Enter Your story here"
          type="textarea"
          rows="10"
          cols="10"
          style="resize : none"
        ></textarea>
      </div>
      <div>
        <button class="bg-indigo-700 w-full text-white font-sans rounded shadow-sm py-2">Publish</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        blogTitle: "",
        blogSubtitle: "",
        hashTags: "",
        readingTime: "",
        description: "",
      },
    };
  },
  methods: {
    resetInputFields(){
        this.formData.blogTitle = ""
        this.formData.blogSubtitle = "",
        this.formData.hashTags = "",
        this.formData.readingTime = "",
        this.formData.description = ""
    },
    handleSubmit() {
        console.log(this.formData)
        this.resetInputFields();
    },
  },
};
</script>
