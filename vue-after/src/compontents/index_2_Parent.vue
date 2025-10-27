<script>
import Child from "./index_2_Child.vue"

export default {
    data() {
        return {
            cnt:"content",

            test:"动态数据",
            age:18,

            name:["austoin","Tom","Joni"],

            people:{
                name:"jojo",
                age:18
            },
        }
    },

    components:{
        Child
    }
}

</script>

<template>

    <div :class="cnt">
        <h2>组件传递数据-Parent</h2>

        <child title="Parent 数据传递" demo="测试" :jojo = "test" :age = "age" :name="name" :people="people"/>
        
    </div>


</template>

<style scoped>
    .content {
        display: flex;
        flex-direction: column;
        align-items: center;   
        justify-content: center;
        
        height: 50vh; 
        border: 1px solid #000;
    }
</style>