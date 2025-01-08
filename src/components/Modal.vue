<template>
  <div class="backdrop">
    <div class="modal" :class="{success: theme === 'success', danger: theme === 'danger'}">

      <h2>{{ header }}</h2>
      <p>{{ content }}</p>


    </div>
  </div>
</template>




<script>
  export default {
    props: ['header', 'content', 'theme'],
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
    z-index: 20;
}

.modal {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    max-width: 500px;
    width: 60%;
    text-align: left;
    animation: fadeIn 0.3s ease-in-out;
}

@keyframes fadeIn {
    from {
        opacity: 0;
        transform: scale(0.9);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}

.success {
    background-color: green;
    color: #fff;
}

.danger {
    background-color: crimson;
    color: #fff;
}
</style>