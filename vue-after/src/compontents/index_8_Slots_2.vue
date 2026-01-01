<script>
    export default {
        data() {
            return {
                cnt:'content',
                chileMessage:'chileMessage',
                demoMessage:'demoMessage',

            }
        }
    }
</script>

<template>
    <div class="content">
        <slot name="header" :msg = 'chileMessage'>插槽默认值</slot>

        <slot name="main" :msg = 'demoMessage'>插槽默认值</slot>
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