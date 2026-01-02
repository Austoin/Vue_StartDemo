# Vue_StartDemo - Vue 学习笔记项目

这是一个 Vue 3 学习过程的代码记录项目，包含从基础语法到进阶组件的完整学习路径。

## 📁 项目结构

```
Vue_StartDemo/
├── vue-base/          # Vue 基础知识
├── vue-after/         # Vue 进阶知识
├── img/               # 学习笔记图片
└── *.ipynb            # Jupyter 笔记文件
```

---

## 🟢 vue-base - Vue 基础篇

### 1. 模板语法与属性绑定
**文件**: [`index_1.vue`](vue-base/src/compoennts/index_1.vue)

| 语法 | 说明 | 示例 |
|------|------|------|
| `{{ }}` | 插值表达式 | `{{ msg }}` |
| `v-html` | 渲染 HTML | `<p v-html="raw"></p>` |
| `:attr` / `v-bind:attr` | 属性绑定 | `:class="col"` |
| `v-bind="obj"` | 批量绑定属性 | `v-bind="boID"` |

---

### 2. 条件渲染
**文件**: [`index_2_ifshow.vue`](vue-base/src/compoennts/index_2_ifshow.vue)

| 指令 | 说明 |
|------|------|
| `v-if` | 条件为 true 时渲染元素，false 时销毁 |
| `v-else-if` | 多条件判断 |
| `v-else` | 条件为 false 时渲染 |
| `v-show` | 通过 CSS `display` 切换显示/隐藏 |

**区别**：
- `v-if` 有更高的**切换开销**（销毁/重建）
- `v-show` 有更高的**初始渲染开销**（始终渲染）

---

### 3. 列表渲染
**文件**: [`index_3_list.vue`](vue-base/src/compoennts/index_3_list.vue)

```html
<!-- 遍历数组 -->
<p v-for="(value, index) in array">{{ value }}</p>

<!-- 遍历对象 -->
<p v-for="(value, key, index) in object">{{ key }}: {{ value }}</p>

<!-- 遍历 JSON 数组 -->
<div v-for="item in jsonArray">{{ item.title }}</div>
```

---

### 4. Key 的作用
**文件**: [`index_4_keyDemo.vue`](vue-base/src/compoennts/index_4_keyDemo.vue)

- `key` 帮助 Vue 识别节点，优化 DOM 更新
- 推荐使用**唯一 ID** 作为 key，而非 index
- 避免就地更新，提高渲染性能

```html
<p v-for="item in list" :key="item.id">{{ item.title }}</p>
```

---

### 5. 事件处理
**文件**: [`index_5_v-on.vue`](vue-base/src/compoennts/index_5_v-on.vue)

| 类型 | 语法 | 示例 |
|------|------|------|
| 内联处理器 | 直接写表达式 | `@click="count++"` |
| 方法处理器 | 调用 methods 中的方法 | `@click="addCount"` |

```html
<button v-on:click="count++">Add</button>
<button @click="addCount">Add</button>  <!-- 简写 -->
```

---

### 6. 事件传参
**文件**: [`index_6_event.vue`](vue-base/src/compoennts/index_6_event.vue)

```html
<!-- 自动传入 event 对象 -->
<button @click="handleClick">Click</button>

<!-- 手动传参 + event 对象 -->
<p @click="getName(value, $event)">{{ value }}</p>
```

---

### 7. 事件修饰符
**文件**: [`index_7.vue`](vue-base/src/compoennts/index_7.vue)

| 修饰符 | 作用 |
|--------|------|
| `.prevent` | 阻止默认行为 (`e.preventDefault()`) |
| `.stop` | 阻止事件冒泡 (`e.stopPropagation()`) |
| `.once` | 只触发一次 |
| `.self` | 只在自身触发 |

```html
<a @click.prevent="handleClick" href="...">链接</a>
<p @click.stop="clickP">阻止冒泡</p>
```

---

### 8. 数组变化侦听
**文件**: [`index_8_ArrayList.vue`](vue-base/src/compoennts/index_8_ArrayList.vue)

**变更方法**（会触发视图更新）：
- `push()`, `pop()`, `shift()`, `unshift()`
- `splice()`, `sort()`, `reverse()`

**替换方法**（需要重新赋值）：
```javascript
this.name = this.name.concat(['新元素'])
```

---

### 9. 计算属性
**文件**: [`index_9_Compute.vue`](vue-base/src/compoennts/index_9_Compute.vue)

```javascript
computed: {
    isYes() {
        return this.list.length > 2 ? 'Yes' : 'No'
    }
}
```

**优点**：
- 基于响应式依赖进行**缓存**
- 多次使用只计算一次
- 比 methods 更高效

---

### 10. Class 绑定
**文件**: [`index_10_Class.vue`](vue-base/src/compoennts/index_10_Class.vue)

```html
<!-- 对象语法 -->
<p :class="{ 'active': isActive, 'danger': isDanger }">文本</p>

<!-- 数组语法 -->
<p :class="[activeClass, dangerClass]">文本</p>

<!-- 混合使用 -->
<p :class="[isActive ? 'active' : '', { 'danger': isDanger }]">文本</p>
```

---

### 11. Style 绑定
**文件**: [`index_11_Style.vue`](vue-base/src/compoennts/index_11_Style.vue)

```html
<!-- 对象语法 -->
<p :style="{ color: colorVar, fontSize: sizeVar }">文本</p>

<!-- 绑定对象 -->
<p :style="styleObject">文本</p>

<!-- 数组语法 -->
<p :style="[styleObj1, styleObj2]">文本</p>
```

> ⚠️ 推荐使用 class 绑定，style 权重过高不易维护

---

### 12. 侦听器 Watch
**文件**: [`index_12_Watch.vue`](vue-base/src/compoennts/index_12_Watch.vue)

```javascript
watch: {
    message(newVal, oldVal) {
        console.log('新值:', newVal, '旧值:', oldVal)
    }
}
```

**用途**：监听数据变化，执行异步操作或复杂逻辑

---

### 13. 表单绑定 v-model
**文件**: [`index_13_Model.vue`](vue-base/src/compoennts/index_13_Model.vue)

```html
<input type="text" v-model="message">
<input type="text" v-model.lazy="message">  <!-- 失焦/回车后更新 -->
<input type="checkbox" v-model="checked">
```

**修饰符**：
- `.lazy` - 在 change 事件后同步
- `.number` - 转换为数字
- `.trim` - 去除首尾空格

---

## 🔵 vue-after - Vue 进阶篇

### 1. 模板引用 ref
**文件**: [`index_1_ModelRef.vue`](vue-after/src/compontents/index_1_ModelRef.vue)

```html
<div ref="cont">内容</div>
<input ref="username" type="text">

<script>
methods: {
    getDemo() {
        console.log(this.$refs.cont.innerHTML)
        console.log(this.$refs.username.value)
    }
}
</script>
```

---

### 2. 组件通信 - Props（父传子）
**文件**: [`index_2_Parent.vue`](vue-after/src/compontents/index_2_Parent.vue) / [`index_2_Child.vue`](vue-after/src/compontents/index_2_Child.vue)

**父组件**：
```html
<Child title="标题" :age="18" :list="array" :obj="object" />
```

**子组件**：
```javascript
props: ["title", "age", "list", "obj"]
```

---

### 3. Props 校验
**文件**: [`index_3_CompontB.vue`](vue-after/src/compontents/index_3_CompontB.vue)

```javascript
props: {
    title: {
        type: [String, Number],  // 类型
        required: true           // 必填
    },
    age: {
        type: Number,
        default: 0               // 默认值
    },
    list: {
        type: Array,
        default() {              // 数组/对象默认值用函数
            return []
        }
    }
}
```

---

### 4. 组件事件 $emit（子传父）
**文件**: [`index_4_Compont.vue`](vue-after/src/compontents/index_4_Compont.vue) / [`index_4_Event.vue`](vue-after/src/compontents/index_4_Event.vue)

**子组件**：
```javascript
this.$emit('someEvent', data)
```

**父组件**：
```html
<Child @someEvent="handleEvent" />
```

---

### 5. 组件事件配合 v-model
**文件**: [`index_5_Main.vue`](vue-after/src/compontents/index_5_Main.vue) / [`index_5_Search.vue`](vue-after/src/compontents/index_5_Search.vue)

```javascript
// 子组件：监听数据变化，实时发送
watch: {
    search(newVal) {
        this.$emit('searchEvent', newVal)
    }
}
```

---

### 6. Props 传递函数（另一种子传父）
**文件**: [`index_6_ComA.vue`](vue-after/src/compontents/index_6_ComA.vue) / [`index_6_ComB.vue`](vue-after/src/compontents/index_6_ComB.vue)

```html
<!-- 父组件传递函数 -->
<Child :sendMsg="handleMsg" />

<!-- 子组件调用函数 -->
<p>{{ sendMsg(data) }}</p>
```

---

### 7. 透传 Attributes
**文件**: [`index_7_Attributes.vue`](vue-after/src/compontents/index_7_Attributes.vue)

- 父组件传递的属性会自动透传到子组件根元素
- 只对**单根节点**组件生效
- 可通过 `inheritAttrs: false` 禁用

---

### 8. 插槽 Slots
**文件**: [`index_8_Slots_1.vue`](vue-after/src/compontents/index_8_Slots_1.vue) / [`index_8_Slots_2.vue`](vue-after/src/compontents/index_8_Slots_2.vue)

**具名插槽**：
```html
<!-- 子组件 -->
<slot name="title"></slot>
<slot name="content"></slot>

<!-- 父组件 -->
<Child>
    <template #title>标题内容</template>
    <template v-slot:content>正文内容</template>
</Child>
```

**作用域插槽**：
```html
<!-- 子组件 -->
<slot name="header" :msg="childData"></slot>

<!-- 父组件 -->
<template #header="slotProps">
    {{ slotProps.msg }}
</template>
```

---

### 9. 生命周期
**文件**: [`index_9_User.vue`](vue-after/src/compontents/index_9_User.vue)

| 阶段 | 钩子函数 | 说明 |
|------|----------|------|
| 创建期 | `beforeCreate` | 实例初始化之前 |
| | `created` | 实例创建完成，可访问 data |
| 挂载期 | `beforeMount` | 挂载之前 |
| | `mounted` | 挂载完成，可访问 DOM |
| 更新期 | `beforeUpdate` | 数据更新之前 |
| | `updated` | 数据更新完成 |
| 销毁期 | `beforeUnmount` | 卸载之前 |
| | `unmounted` | 卸载完成 |

---

### 10. 动态组件
**文件**: [`index_10_ComponentA.vue`](vue-after/src/compontents/index_10_ComponentA.vue) / [`index_10_ComponentB.vue`](vue-after/src/compontents/index_10_ComponentB.vue)

```html
<component :is="currentComponent"></component>
<button @click="switchComponent">切换</button>
```

```javascript
data() {
    return {
        currentComponent: 'ComponentA'
    }
},
methods: {
    switchComponent() {
        this.currentComponent = this.currentComponent === 'ComponentA' 
            ? 'ComponentB' 
            : 'ComponentA'
    }
}
```

---

## 🛠️ 项目配置

### vue-base
- **Vue 3** 基础项目
- **Vite** 构建工具
- 无路由、无状态管理

### vue-after
- **Vue 3** + **Vue Router** + **Pinia**
- **Vite** 构建工具
- **ESLint** + **Prettier** 代码规范

---

## 🚀 快速开始

```bash
# 进入项目目录
cd vue-base  # 或 cd vue-after

# 安装依赖
npm install

# 启动开发服务器
npm run dev
```

---

## 📚 知识点总结

### Vue 基础
1. 模板语法：插值、v-html、属性绑定
2. 条件渲染：v-if / v-show
3. 列表渲染：v-for + key
4. 事件处理：v-on / @ + 修饰符
5. 数据绑定：v-model
6. 计算属性：computed
7. 侦听器：watch
8. 样式绑定：class / style

### Vue 进阶
1. 模板引用：ref / $refs
2. 组件通信：props（父传子）、$emit（子传父）
3. Props 校验：type、required、default
4. 插槽：具名插槽、作用域插槽
5. 生命周期：8 个钩子函数
6. 动态组件：`<component :is="">`
7. 透传属性：inheritAttrs

---

## 📝 学习建议

1. **先学 vue-base**：掌握 Vue 基础语法
2. **再学 vue-after**：理解组件化开发
3. **动手实践**：修改代码，观察效果
4. **查阅官方文档**：[Vue.js 官方文档](https://cn.vuejs.org/)

---

## 📄 License

MIT License - 仅供学习使用