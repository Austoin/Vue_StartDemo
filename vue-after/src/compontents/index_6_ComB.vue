<script>
    export default {
        data() {
            return {
                msg:"send the data",
            }
        },
        props:{
            title:{
                type:String,
            },
            sendMsg:{
                type:Function,
            }
        }
    }
</script>
<template>
    <h3>子组件</h3>
    <p>{{ sendMsg(msg) }}</p>
</template>