<script>

export default {
    data() {
        return {
            
            }
    },
    
    props:{
        title:{
            type:[String,Number,Object,Array],

            // 不传的时候终端就会报警告，必选项
            required:true
        },

        // 没传的时候就设置默认值
        age:{
            type:Number,
            default:0
        },

        // 数组和对象默认值采用函数的形式
        name:{
            type:Array,
            default(){
                return ["空的"]
            }
        }
    }

}

</script>

<template>

    <div>
        <h2>B</h2>

        <!-- 父元素传过来的数据不可修改 -->
        <p>{{ title }}</p>
        <p>{{ age }}</p>
        <ul>
            <li v-for="(value, index) in name" :key="index">{{ value }} -- {{ index }}</li>
        </ul>
    </div>


</template>

<style scoped>

</style>