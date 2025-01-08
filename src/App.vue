<template>

  <h1 ref="title">
    helloAll
  </h1>

  <input type="text" ref="focus">
  <button @click="clickHandler" ref="name">click</button>

  <AppModal 
  :header="header"
  :content="content"
  :theme="theme" ></AppModal>

</template>



<script>
import AppModal from './components/AppModal.vue';

export default {

  data(){
    return {
      header: "Login Success",
      content: "Welocome all users",
      theme: "success"
      // theme: "fail"
    }
  },

  components: { AppModal },
 
  methods:{
    clickHandler(){
      // console.log(this.$refs.name)
      this.$refs.name.textContent = "clicked",
      this.$refs.title.textContent = "Hi there, changed it",
      this.$refs.focus.focus()
    }
  },

}
</script>

<style>

</style>