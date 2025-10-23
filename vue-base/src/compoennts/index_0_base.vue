<script>
export default {
    data() {
        return {
           cnt: "content",

        }
    },

    methods: {
       

}
}

</script>

<template>
    <div :class="cnt">
        <h2></h2>
        
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