<script>
import CompontB from './index_3_CompontB.vue';

export default {
    data() {
        return {
            cnt:"content",
            name:"JoJo"
        }
    },



    components:{
        CompontB
    }
}

</script>

<template>

    <div :class="cnt">
        <h2>A</h2>

        <CompontB :title="name" />
        
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