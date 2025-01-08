<template>

    <div class="modal"
    :class="{success: theme ==='success' , 
    fail: theme === 'fail' }">

        <h2>{{ header }}</h2>
        <p>{{ content }}</p>
    </div>
  
</template>

<script>
    export default {
        
    props: ['header', 'content', 'theme']

    }
</script>

<style scoped>

    .modal {
        background-color: #f4ae16;
        padding: 20px;
        border-radius: 12px;
        text-align: center;
        box-shadow: 0 6px 12px rgba(75, 76, 76, 0.632);
        transition: all 0.3s ease;
        max-width: 500px;
        margin: auto;
        width: 60%;
    }

    /* Add a title animation for the modal appearance */
    .modal {
        animation: fadeIn 0.5s ease-out;
    }

    /* Modal fade-in effect */
    @keyframes fadeIn {
        from {
            opacity: 0;
            transform: translateY(-10px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    .success {
        background-color: #017364;
        color: #fff;


    }

    .fail {
        background-color: #e91e63;
        color: #fff;
    }

</style>
