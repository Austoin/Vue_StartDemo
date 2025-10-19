<script>

    export default {
        data() {
            return {
                cnt: "content",

                code:["python", "javascript", "golang"],

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
                    {
                        "id": 3141592,
                        "title": "探索山城的另一面｜重庆不仅有火锅🍲还有森林秘境",
                        "avator": "https://pic.qyer.com/avatar/123/45/67/89/200?v=1687123456"
                    },
                    {
                        "id": 2718281,
                        "title": "周末去哪儿☀️｜打卡帝都新晋网红艺术展🎨超出片！",
                        "avator": "https://pic.qyer.com/avatar/098/76/54/32/200?v=1699876543"
                    }
                ],

            }
        }
    }
    
</script>

<template>
    <div :class="cnt">
        <h2>列表渲染</h2>

        <p v-for="(value, index) in code">{{ value }} ---- index: {{ index }}</p>
        
        <div v-for="value in result">     <!-- in 可以改成 of -->
            <p>
                {{ value.title }} 
            </p>
            <img :src="value.avator">   <!-- 图片不显示不是错误，只是变成了0x0，在官网才能显示 -->
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