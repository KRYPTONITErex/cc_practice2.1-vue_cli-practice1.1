<template>

  <div>
    <h1>{{title}}</h1>
    <h1 ref="greet">hello</h1>
  </div>

  <input type="text" ref="name">
  <button @click="clickHandler">click</button>

  <Modal 
    :header="header" 
    :content="content"
    :theme="theme">
  </Modal>


</template>

<script>

  import Modal from './components/Modal.vue';

  export default {
    data() {
      return {
        header: "Login is success",
        content: "Welcome user KoLwinPhyo",
        // theme: "success",
        theme: "danger"
      }
    },
    methods: {
      clickHandler(){
        // console.log(this.$refs.name)
        this.$refs.name.focus(),
        this.$refs.greet.textContent = "hi , hello , hey"
      }
    },
    components: {
      Modal
    }

  }
</script>

<style>

  h1{
    color: red;

  }
  div{
    color: green;

  }

</style>