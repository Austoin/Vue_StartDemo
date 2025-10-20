<script>
export default {
    data() {
        return {
           cnt: "content",

        }
    },

    methods: {
        cleckhttp(e){

            // 通过event对象阻止跳转
            e.preventDefault();
            
            console.log("click + 1")
        },

        cleckhttp_2(){

            // 通过修饰符的方法阻止跳转
            console.log("click + 1")
        },

        clickDiv(){
            console.log("Div")
        },

        clickP(){
            console.log("P")
        },

    },


}

</script>

<template>
    <div :class="cnt">
        <h2>事件修饰符</h2>

        <!-- 阻止事件 -->
        <a @click="cleckhttp" href="https://cn.vuejs.org/guide/essentials/event-handling.html">修饰符官网</a>

        <a @click.prevent="cleckhttp_2" href="https://cn.vuejs.org/guide/essentials/event-handling.html">修饰符官网</a>

        <!-- 冒泡事件 -->
        <!-- 点击p标签div标签也会触发就是冒泡事件 -->
        <div @click="clickDiv">
            <p @click.stop="clickP">冒泡测试</p>  <!-- 和在clickP方法使用e.stopPropagation()等效 -->
        </div>

        <!-- 其余修饰符见官网 -->
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