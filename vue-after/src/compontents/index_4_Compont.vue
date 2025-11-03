<script>
import index_4_Event from './index_4_Event.vue';

export default {
    data() {
        return {
            cnt:"content",
            
            
            message:"",
        }
    },

    components:{
        index_4_Event
    },
    methods:{
        getEvent(data){
            this.message = data;
        }
    }
}

</script>

<template>

    <div :class="cnt">
        <h2>组件事件</h2>
        <!-- 可以实现子传父 -->
        
        <index_4_Event @someEvent="getEvent"/>
        <p>父元素：{{ message }}</p>
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