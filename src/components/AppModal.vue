<template>

    <div class="backdrop" @click.self="closeModal">
        <div class="modal" 
        :class="{success: theme ==='success' , 
        fail: theme === 'fail' }">

            <!-- <h2>{{ header }}</h2>
            <p>{{ content }}</p> -->

            <slot>default
              <h3>check your input again</h3>
            </slot>
            <slot name="links"></slot>

        </div>
    </div>
  
</template>

<script>
    export default {
        
    props: [ 'theme'],
    methods: {
        closeModal(){
            this.$emit('closeModal')
        }
    }

    }
</script>

<style scoped>

.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal {
  position: relative;
  background-color: #ffffff;
  padding: 20px 25px;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.25);
  transition: transform 0.3s ease, opacity 0.3s ease;
  max-width: 400px;
  width: 80%;
  animation: fadeIn 0.5s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.success {
  background-color: #017364;
  color: #ffffff;
}

.fail {
  background-color: #e91e63;
  color: #ffffff;
}

h2 {
  color: #ffffff;
  font-size: 24px;
  margin-bottom: 10px;
  font-weight: bold;
  font-family: 'Courier New', Courier, monospace;
}

p {
  color: #ffffff;
  font-size: 16px;
  margin-top: 10px;
  line-height: 1.5;
  font-family: Arial, sans-serif;
}

button {
  position: absolute;
  top: 10px;
  right: 10px;
  background-color: transparent;
  border: none;
  font-size: 18px;
  color: #ffffff;
  cursor: pointer;
  transition: color 0.3s ease;
}

button:hover {
  color: #ffcccb;
}

</style>