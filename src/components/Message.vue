<template>
    <div v-show="message" class="message-container">
        <p v-html="message"></p>
    </div>
</template>

<script>
export default {
    name: "Message",
    data(){
        return{
            message: null
        }
    },
    props: {
        msg: String
    },
    methods: {
        clearMessage() {
            setTimeout(() => {
                this.message = ""
            }, 3000);
        }
    },
    watch: { 
        msg: function(newVal, oldVal) { 
            this.message = newVal;
            this.clearMessage();
        }
    }
    
}
</script>

<style scoped>
    .message-container {
        color: #004085;
        background-color: #cce5ff;
        border: 2px solid #b8daff;
        border-radius: 5px;
        padding: 10px;
        max-width: 400px;
        margin: 30px auto;
    }
</style>