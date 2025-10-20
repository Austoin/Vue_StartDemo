<script>
export default {
    data() {
        return {
            cnt: "content",

            count_1: 0,

            count_2: 0,
        }
    },

    // 以后所有的方法都写这里
    methods: {
        addCount() {
            // console.log("点击了！")
            this.count_2++
        }
    }

// //  vue3 写法, 但需要将标签改成setup才能识别
// import { ref } from 'vue' // 1. 从 vue 导入 ref

// // 使用 <script setup> 语法糖，代码更简洁
// const cnt = "content"

// // 2. 使用 ref() 创建响应式变量，替代了 data()
// const count_1 = ref(0)
// const count_2 = ref(0)

// // 3. 直接定义函数，替代了 methods 对象
//  function addCount() {
// // 4. 修改响应式变量的值需要通过 .value 属性
//     count_2.value++

}

</script>

<template>
    <div :class="cnt">
        <h2>内联事件处理器</h2>

        <p>{{ count_1 }}</p>
        <button v-on:click="count_1++">Add</button>

        <h2>方法事件处理器</h2>
        <p>{{ count_2 }}</p>
        <button @click="addCount">Add</button>

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