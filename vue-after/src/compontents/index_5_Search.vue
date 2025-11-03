<script>

export default {
    data() {
        return {
            search: '',
        }
    },
    watch:{
        search(newVal){
            this.$emit('searchEvent', newVal)
        }
    }
    

}

</script>

<template>
    <h2>Main</h2>
    <h3>搜索框</h3>
    <input type="text" v-model="search">
</template>