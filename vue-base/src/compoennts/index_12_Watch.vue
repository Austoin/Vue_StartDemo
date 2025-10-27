<script>
export default {
    data() {
        return {
           cnt: "content",

           message: "Hello JOJO",

        }
    },

    methods: {
       
        ChangeMethods() {
            this.message = "Hi JOJO"
        }

    },

    watch: {
        message(newData, oldData){
            console.log(newData, oldData)
        }
    }
}

</script>

<template>
    <div :class="cnt">
        <h2>侦听器</h2>

        <p>{{message}}</p>
        <button @click="ChangeMethods">change</button>
        
    </div>


</template>

<style>

    .content {
        display: flex;
        flex-direction: column;
        align-items: center;   
        justify-content: center;
        
        height: 50vh; 
        border: 1px solid #000;
    }

</style>