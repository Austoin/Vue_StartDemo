<script>
export default {
    data() {
        return {
            cnt:"rd",
        }
    },

    props:["title","demo","jojo","age","name","people"],
}

</script>

<template>
    <div>
        <h2>组件传递数据-Child</h2>

        <!-- 数组，数字，对象等都可以传递 -->

        <p>{{ title }}</p>
        <p>{{ demo }}</p>
        <p  :class="cnt">{{ jojo }} --- {{ age }}</p>

        <ul>
            <li v-for = "(value,index) in name" :key="index">{{ value }} -- {{ index }}</li>
        </ul>

        <!-- 对象 -->
        <p>{{ people.name }}</p>
        <p>{{ people.age }}</p>
        
    </div>


</template>

<style scoped>

    .rd {
        font-size: 30px;
        color: blueviolet;
    }

</style>