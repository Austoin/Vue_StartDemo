<script>
    export default {
        data() {
            return {
                cnt:'content',
            }
        },

        beforeCreate(){
            console.log('beforeCreate -- 创建期')
        },
        created(){
            console.log('create -- 创建期')
        },

        beforeMount(){
            console.log('beforeMount -- 挂载期')
        },
        mounted(){
            console.log('mount -- 挂载期')
            console.log(this.$refs.name)
        },

        beforeUpdate(){
            console.log('beforeUpdate -- 更新期')
        },
        updated(){
            console.log('update -- 更新期')
        },

        beforeUnmount(){
            console.log('beforeUnmount -- 销毁期')
        },
        unmounted(){
            console.log('unmounted -- 销毁期')
        }
    }
</script>

<template>
    <div class="content">
        <h3>组件生命周期函数应用</h3>
        <p ref="name">Austoin</p>
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