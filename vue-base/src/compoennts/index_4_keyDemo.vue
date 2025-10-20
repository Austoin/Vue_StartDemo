<script>
export default {
    data() {
        return {
            name: ["Austoin", "Tom", "Kiti"], 

            cnt: "content", 

            color: "mr",

            res: [
                {
                    id: 123456,
                    title: "啥事给",
                    content: "因陀罗"
                },

                {
                    id: 456789,
                    title: "哪里痛",
                    content: "阿修罗"
                }
            ],
        }
    },
}
</script>

<template>
    <div :class="cnt">

        <!-- 主要是在vue中调换列表元素的信息会重新渲染，使用key就只会调用顺序达到目的了 -->

        <h2>key在v-for的应用</h2>  

        <!-- key应用索引 -->
        <p v-for="(value, index) in name" :key="index" :class="color"> {{ value }}---{{ index }} </p>  

        <!-- 这里看起来无变化，只是更新的时候不会就地更新重新渲染，而是通过key调换顺序减少内存消耗 -->

        <!-- id是不变的，常用的key也是请求json -->
        <p v-for="value in res" :key="value.id">{{ value.id }}---{{ value.title }}---{{ value.content }}</p>

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

    .mr{
        color: blueviolet;
        font-family: 'Times New Roman', Times, serif;
    }

</style>