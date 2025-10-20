<script>

    export default {
        data() {
            return {
                cnt: "content",

                code:["python", "javascript", "golang"],


                // json格式
                result: [
                    {
                        "id": 2261677,
                        "title": "鄂尔多斯｜感受一座城市的璀璨夜景 感受一座城市，除了白日里的车水马龙，喧嚣繁华之",
                        "avator": "https://c-ssl.duitang.com/uploads/item/202007/20/20200720004023_xnbun.jpg"
                                                  },
                    {
                        "id": 2261566,
                        "title": "🔥咖啡🌟人必，成都这家洞穴暗黑风咖啡厅酷毙了!!早C晚A走起☕成都天气这么热",
                        "avator": "https://pic.qyer.com/avatar/011/07/08/69/200?v=1572185180"
                    },
                ],

                //对象格式
                userInfo: {
                    name: "Austoin",
                    power: "123456789",
                }

            }
        }
    }
    
</script>

<template>
    <div :class="cnt">
        <h2>列表渲染</h2>

        <p v-for="(value, index) in code">{{ value }} ---- index: {{ index }}</p>
        

        <!-- v-for 还可以便利对象 -->
        <div v-for="value in result">     <!-- in 可以改成 of -->
            <p>
                {{ value.title }} 
            </p>
            <img :src="value.avator">   <!-- 图片不显示不是错误，只是变成了0x0，在官网才能显示 -->
        </div>

        <!-- v-for 还可以便利对象 -->
        <div>
            <p v-for="(value, key, index) in userInfo">{{ value }}------{{ key }}------{{ index }}</p>
        </div>
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