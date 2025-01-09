<template>

  <h1 ref="title">
    helloAll
  </h1>

  <input type="text" ref="focus">
  <button @click="clickHandler" ref="name">click</button>

  <div v-if="showModal">
    <AppModal 
      :header="header"
      :content="content"
      :theme="theme" 
      @closeModal="showModal = false">

      <h2>Want to Log Out?</h2>
      <p>See you all users !!</p>

      <template v-slot:links>
        <a href="">SignUp</a><a href="">LogIn</a>
      </template>

    </AppModal>
  </div>
  <button id="btn" @click="showModal=!showModal" >Close Modal</button>

  <div v-if="showModalLP">
    <AppModal 
      :header="header"
      :content="content"
      theme="success" 
      @closeModal="showModalLP = false">

      <h2>Log in is successful</h2>
      <p>Welcome KO LWIN !!</p>

      <template v-slot:links>
        <a href="">SignUp</a><a href="">LogIn</a>
      </template>

    </AppModal>
  </div>
  <button @click="showModalLP=!showModalLP" >Open Modal LP</button>

</template>



<script>
import AppModal from './components/AppModal.vue';

export default {

  data(){
    return {
      header: "Login Success",
      content: "Welocome all users",
      // theme: "success",
      theme: "fail",
      showModal: false,
      showModalLP: false
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

<style scoped>

h1 {
  font-size: 24px;
  color: #2c3e50;
  text-align: center;
  margin-bottom: 20px;
  font-family: 'Arial', sans-serif;
}

input {
  display: block;
  margin: 10px auto;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 80%;
  font-size: 16px;
}

button {
  display: block;
  margin: 10px auto;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  color: #fff;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:first-of-type {
  background-color: #3498db;
}

button:first-of-type:hover {
  background-color: #2980b9;
}

button:last-of-type {
  background-color: #2ecc71;
}

button:last-of-type:hover {
  background-color: #27ae60;
}

div {
  margin-top: 20px;
  text-align: center;
}

#btn {
  background-color: #e74c3c;
}

#btn:hover {
  background-color: #c0392b;  
}

</style>