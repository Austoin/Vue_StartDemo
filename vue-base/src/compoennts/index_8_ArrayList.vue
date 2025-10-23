<script>
export default {
    data() {
        return {
           cnt: "content",

           name:['Austoin', 'Tom', 'Jerrey'],

        }
    },

    methods: {

        Add(){
            // 变更方法添加名字
            // this.name.push('Surkar')

            // 替换方法添加名字
            //this.name.concat(['Surkar']) //相当于合并一个数组,虽然添加了，但不会显示在UI,也就是原数组没有发生变化
            //console.log(this.name.concat(['Surkar']))

            this.name = this.name.concat(['Surkar'])  // 这样用替换方法也可以改变UI，即改变原数组，具体看img的1，2
        },

    }
}

</script>

<template>
    <div :class="cnt">
        <h2>数组变化侦听</h2>
        <button @click="Add">添加信息</button>
        <ul>
            <li v-for="(value, index) in name" key="index">{{ value }}---{{ index }}</li>
        </ul>
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