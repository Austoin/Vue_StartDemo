<script>
export default {
    data() {
        return {
           cnt: "content",

           isActivate: true,

           isDanger: true,

           both:{

            'activate':true,
            'text-danger':true,

           },

           ActivateArr:'activate',
           TextArr:'text-danger',

        }
    },

    methods: {
       

    }
}

</script>

<template>
    <div :class="cnt">
        <h2>Class 样式绑定</h2>
        <p :class="{'activate': isActivate, 'text-danger': isDanger}"> 扣喏 dio 哒</p>

        <p :class="both">嗨到不行</p> <!-- 多个对象绑定 -->

        <p :class="[ActivateArr, TextArr]">你给油打路</p> <!-- 数组绑定 -->

        <!-- <p :class="[isActivate ? 'activate text-danger' : '']">你给油打路</p> -->

        <!-- 数组嵌套对象 -->
        <!-- <p :class="[isActivate ? 'activate' : '', {'text-danger': isDanger}]">你给油打路</p> -->
        
    </div>


</template>

<style>

    .activate {
        font-size: 40px;
    }

    .text-danger {
        color: red;
    }

    .content {
        display: flex;
        flex-direction: column;
        align-items: center;   
        justify-content: center;
        
        height: 50vh; 
        border: 1px solid #000;
    }

</style>