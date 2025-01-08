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
  <button @click="showModal = !showModal">show modal</button>


  <div v-if="showModalLP">
    <Modal 
      :header="header" 
      :content="content"
      :theme="theme"
      @closeModal="showModalLP = !showModalLP">
    
      <h1>This is KO Lwin Phyo success</h1>
      <p>Congratulations</p>

      <template v-slot:links>
        <a href="">Sign Up</a>
        <a href="">Login</a>
      </template>
    </Modal>

  </div>
  <button @click="showModalLP = !showModalLP">Lwin Phyo Modal</button>


</template>

<script>

  import Modal from './components/Modal.vue';

  export default {
    data() {
      return {
        header: "Login is success",
        content: "Welcome user KoLwinPhyo",
        // theme: "success",
        theme: "danger",
        showModal: false,
        showModalLP: false
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

  div{
    color: green;

  }

</style>