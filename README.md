# vuex-start

## vuex 概述

### 1. 组件之间共享数据的方式

- 父向子传值：```v-bind``` 属性绑定
- 子向父传值: ```v-on``` 事件绑定
- 兄弟组件之间共享数据： ```EventBus```

### 2. vuex是什么？
&ensp; &ensp; vuex 是实现组件全局状态（数据）管理的一种机制，可以方便的实现组件之间的数据共享。

### 3. 使用vue统一管理状态的好处
- 能够在vuex中集中管理共享的数据，易于开发和后期维护
- 能够高效的实现组件之间的数据共享，提高开发效率
- 存储在vuex中的数据都是响应式的，能够实时保持数据与页面的同步

## vuex核心概念
### 1. state
&ensp; &ensp; state提供唯一的公共数据资源，所有共享的数据都要统一放到store的state中进行存储。

&ensp; &ensp;组件中访问state中数据的方式有两种：
- ```this.$store.state.全局数据名称```
- 从vuex中导入mapState函数&ensp;  ```import { mapState } from 'vuex'``` 通过导入的mapState函数，将当前组件需要的全局数据，映射为当前组件的computed计算属性。
    ```
    computed: {
        ...mapState(['全局数据名称'])
    }
    ```
### 2. mutation
&ensp; &ensp; mutation用于变更store中的数据 (且只能通过mutation修改数据)。
- vuex规定只能通过mutation变更store数据，不可以直接操作store中的数据
- 通过mutation变更数据的做法可以集中监控所有数据的变化

&ensp; &ensp; 触发mutations的两种方式
- ```this.$store.commit('定义在mutations中的函数名')```，   commit 用来触发mutation中的函数
- 从vuex中导入mapMutations函数  ```import { mapMutations } from 'vuex'``` 通过导入的mapMutations函数，将当前组件需要的mutations函数，映射为当前组件的methods方法。
    ```
    methods: {
        ...mapMutations(['mutations中函数名称'])
    }
    ```
### 3. action
&ensp; &ensp; action用于处理异步任务。但是不能在action定义的函数中直接修改state中的数据，须通过context.commit('mutation中定义的函数') 触发mutation

&ensp; &ensp; actions触发方式：
- ```this.$store.dispatch('action中的异步函数')```, dispatch用来触发action中的函数
- 从vuex中导入mapActions函数 ```import { mapActions } from 'vuex' ```通过导入的mapActions函数，将当前组件需要的actions函数，映射为当前组件的methods方法。
    ```
    methods: {
        ...mapactions(['actions中函数名称'])
    }
    ```
### 4. getter