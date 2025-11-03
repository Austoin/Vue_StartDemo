<script>
import index_5_Search from './index_5_Search.vue';

export default {
    data() {
        return {
            cnt:"content",

            val:"",
        }
    },

    components:{
        index_5_Search
    },
    methods: {
        getSearch(data){
            this.val = data;
        }
    }

}

</script>

<template>

    <div :class="cnt">
        <h2>组件事件配合v-model使用</h2>
        <index_5_Search @searchEvent="getSearch"/>
        <h3>搜索子组件获取到的内容：{{ val }}</h3>
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