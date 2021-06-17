<template>
  <div>
    <h2>当前最新的count值为：{{count}}</h2>
    <button @click="sub">-1</button><br/><br/>
    <button @click="subN(8)">-n</button><br/><br/>
    <button @click="subAsync">async-1</button><br/><br/>
    <button @click="subNAsync(5)">async-n</button><br/><br/>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions } from 'vuex'
export default {
  data () {
    return {

    }
  },
  computed: {
    ...mapState(['count'])
  },
  methods: {
    ...mapMutations(['sub', 'subN']),
    ...mapActions(['subAsync', 'subNAsync'])
  }
}
</script>
