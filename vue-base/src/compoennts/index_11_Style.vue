<script>
export default {
    data() {
        return {
           cnt: "content",

           colorDemo: "red",
           fontSize: "30px",

           styleBoth:{
             color: "red",
             fontSize: "30px",
           }

        }
    },

    methods: {
       

    },

    computed: {


    }
}

</script>

<template>
    <div :class="cnt">
        <h2>Style 绑定</h2>

        <p :style="{color: colorDemo, fontSize: fontSize}">JOJO</p>

        <!-- 绑定对象 -->
        <p :style="styleBoth">JOJO</p>

        <!-- 绑定数组 -->
        <p :style="[styleBoth, ]">HI</p>

        <!-- 但更加推荐使用class，style权限太高了后期不易更改 -->
        
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