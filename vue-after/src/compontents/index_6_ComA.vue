<script>
import index_6_ComB from './index_6_ComB.vue';
    export default {
        data() {
            return {
                cnt:"content",
                msg:"",
            }
        },
        components: {
            index_6_ComB
        },
        methods: {
            onEvent(msg) {
                this.msg = msg
            }
        }
    }
</script>
<template>
    <div :class="cnt">
        <h3>使用Props方法子传父</h3>
        <index_6_ComB :sendMsg="onEvent" title="JOJO"/>
        <p>子组件传来的数据：{{msg}}</p>
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