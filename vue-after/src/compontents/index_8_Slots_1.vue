<script>
    export default {
        data() {
            return {
                cnt:'content',

            }
        }
    }
</script>

<template>
    <div class="content">
        <slot name="title"></slot>
        <hr />
        <slot name="content"></slot>
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