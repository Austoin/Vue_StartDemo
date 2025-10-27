<script>
export default {
    data() {
        return {
           cnt: "content",

            contents: "HI JOJO",

        }
    },

    methods: {
       getDemo(){
        console.log(this.$refs.cont.innerHTML = "Hello JOJO")
        console.log(this.$refs.username.value)
       }

    }
}

</script>

<template>
    <div :class="cnt">
        <h2>模板引用</h2>

        <div ref="cont" class="cont">
            {{ contents }}
        </div>
        

        <input type="text" ref="username">

        <button @click="getDemo">获取元素</button>
        
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