<script>
    // import index_1_ModelRef from './compontents/index_1_ModelRef.vue';
    // import index_2_Parent from './compontents/index_2_Parent.vue';
    // import index_3_CompontA from './compontents/index_3_CompontA.vue';
    // import index_4_Compont from './compontents/index_4_Compont.vue';
    // import index_5_Main from './compontents/index_5_Main.vue';
    // import index_6_ComA from './compontents/index_6_ComA.vue';
    // import Index_7_Attributes from './compontents/index_7_Attributes.vue';
    import Index_8_Slots_1 from './compontents/index_8_Slots_1.vue';
    import Index_8_Slots_2 from './compontents/index_8_Slots_2.vue';
 
    export default {
        data(){
            return{
                title:"插槽标题",
                content:"插槽内容",

                currShow:"JOJO is man.",

            }
        },
        components:{
            Index_8_Slots_1,
            Index_8_Slots_2,
        }
    }


// vue3的写法：
// import { ref } from 'vue'
// import index_8_Slots_1 from './compontents/index_8_Slots_1.vue'
// import Index_8_Slots_2 from './compontents/index_8_Slots_2.vue'

// const title = ref("插槽标题")
// const content = ref("插槽内容")
// const currShow = ref("JOJO is man.")

</script>

<template>
    <!-- <index_1_ModelRef />
    <index_2_Parent />
    <index_3_CompontA />
    <index_4_Compont />
    <index_5_Main />
    <index_6_ComA />
    <Index_7_Attributes class="component"/> -->

    <Index_8_Slots_1>
        <template #title>{{ title }}</template>
        <template v-slot:content>{{ content }}</template>
    </Index_8_Slots_1>

    <Index_8_Slots_2>
        <template #header="slotProps">
            <h3>{{ currShow }} -- {{ slotProps.msg }}</h3>
        </template>

        <template #main="slotProps">
            <h3>{{ slotProps.msg }}</h3>
        </template>
    </Index_8_Slots_2>
</template>

<style scoped></style>
