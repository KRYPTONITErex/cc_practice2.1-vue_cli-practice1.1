<template>

  <div>
    <h1>{{title}}</h1>
    <h1 ref="greet">hello</h1>
  </div>

  <input type="text" ref="name">
  <button @click="clickHandler">click</button>

  <div v-if="showModal">
    <Modal 
      :header="header" 
      :content="content"
      :theme="theme"
      @closeModal="showModal = !showModal">
    
      <h1>Login is Successful</h1>
      <p>Welcome users Ko Lwin</p>

      <template v-slot:links>
        <a href="">Sign Up</a>
        <a href="">Login</a>
      </template>
    
    </Modal>
  </div>

  <button @click.shift="showModal = !showModal">show modal</button>


</template>

<script>

  import Modal from './components/Modal.vue';

  export default {
    data() {
      return {
        header: "Login is success",
        content: "Welcome user KoLwinPhyo",
        theme: "success",
        // theme: "danger",
        showModal: false
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
    color: rgb(255, 251, 0);

  }
  div{
    color: green;

  }

</style>