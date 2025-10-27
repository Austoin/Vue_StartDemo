<script>
export default {
    data() {
        return {
           cnt: "content",

           message: "",
           checked: false,

        }
    },

    methods: {
       

    }
}

</script>

<template>
    <div :class="cnt">
        <h2>表单输入绑定</h2>

        <form>

            <input type="text" v-model.lazy="message">  <!-- 回车后显示p标签 -->
            <p>{{ message }}</p>

            <input type="checkbox" id="checkbox" v-model="checked">
            <label for="checkbox">{{ checked }}</label>
        
        
        </form>
        
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