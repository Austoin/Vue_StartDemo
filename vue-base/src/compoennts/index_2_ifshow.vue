<script>

    export default {
        data() {
            return {
                cnt: "content",
                flag: true,
                type:"D"
            }
        },
    }
    
</script>

<template>
    <div :class="cnt">
        <h2>条件渲染</h2>

        <div v-if="flag">看得见 v-if</div>
        <div v-else>看不见 v-if</div>    <!-- 这里如果 flag 是 true 就显示第一条，否者显示第二条 -->

        <div v-if="type == 'A'">A</div>
        <div v-else-if="type == 'B'">B</div>
        <div v-else-if="type == 'C'">C</div>
        <div v-else>NOT A or B or C</div>

        <!-- v-show区别于v-if ， 他是基于display切换的，v-if是基于销毁监听组件，如果为fase则啥也不做，
        v-show不管是不是flase，都会渲染，只是显不显示的问题-->
        <div v-show="flag">看得见 v-show</div> 

         <!-- v-if有更高的切换开销，v-show有更高的渲染开销 -->


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