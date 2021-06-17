<template>
  <div>
    <h2>当前最新的count值为：{{count}}</h2>
    <button @click="sub">-1</button><br/><br/>
    <button @click="subN(8)">-n</button>
  </div>
</template>

<script>
import { mapState, mapMutations } from 'vuex'
export default {
  data () {
    return {

    }
  },
  computed: {
    ...mapState(['count'])
  },
  methods: {
    ...mapMutations(['sub', 'subN'])
  }
}
</script>
