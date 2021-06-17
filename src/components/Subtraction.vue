<template>
  <div>
    <h2>{{showNum}}</h2>
    <button @click="sub">-1</button><br/><br/>
    <button @click="subN(8)">-n</button><br/><br/>
    <button @click="subAsync">async-1</button><br/><br/>
    <button @click="subNAsync(5)">async-n</button><br/><br/>
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions, mapGetters } from 'vuex'
export default {
  data () {
    return {

    }
  },
  computed: {
    ...mapState(['count']),
    ...mapGetters(['showNum'])
  },
  methods: {
    ...mapMutations(['sub', 'subN']),
    ...mapActions(['subAsync', 'subNAsync'])
  }
}
</script>
