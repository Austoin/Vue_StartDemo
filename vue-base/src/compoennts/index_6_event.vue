<script>
export default {
    data() {
        return {
            cnt: "content",

            count: 0,

            name: ["Austoin", "Kiti", "Tom"],

        }
    },

    methods: {
        addCount(e) {

            // vue中的event对象就是js原生Event对象
            console.log(e)
            console.log(e.target)
            e.target.innerHTML = "Add" + "---" + (this.count+1)

            this.count++
        },

        getName(name, e) {

            console.log(name)
            console.log(e)

        },

    }


}

</script>

<template>
    <div :class="cnt">
        <h2>事件传参</h2>

        <p>{{ count }}</p>
        <button @click="addCount">Add</button>

        <!-- 点击页面名字出现在终端 -->
        <!-- 加上$event就可以显示event对象了 -->
        <p @click="getName(value, $event)" v-for="(value, index) in name" key="index">{{ value }} --- {{ index }}</p>


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