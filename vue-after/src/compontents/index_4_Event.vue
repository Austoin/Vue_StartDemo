<script>
export default {
    data() {
        return {
            msg: "child component"
        }
    },

    methods:{
        clikc_SendEvent(){
            this.$emit("someEvent", this.msg)
        }
    }
}

</script>

<template>

    <div>
        <h2>自定义事件</h2>
        <button @click="clikc_SendEvent">发送数据到父元素</button>
        
    </div>


</template>