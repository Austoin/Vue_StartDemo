<script>
export default {
  data() {
    return {
      msg: "Hello",
      raw: "<a href='https://www.baidu.com/'>百度</a>",
      col: "rd",
      boID: {
        class: "rd",

        // 下面还可以写多个属性
      },
    };
  },
};
</script>

<template>
  <div class="content">
    <h2>模板语法 与 属性绑定</h2>

    <p :class="col">{{ msg }}</p>

    <p v-html="raw"></p>

    <button v-bind="boID">BUtton</button>
  </div>
</template>

<style>
.rd {
  color: red;
}

.content {
  display: flex;
  flex-direction: column; /*垂直排列*/
  align-items: center; /*水平居中*/
  justify-content: center; /*垂直居中*/

  height: 50vh;
  border: 1px solid #000;
}
</style>
