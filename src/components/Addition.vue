<template>
  <div>
    <h2>当前最新的count值为：{{$store.state.count}}</h2>
    <button @click="handelAdd">+1</button><br/><br/>
    <button @click="handelAddN">+n</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  methods: {
    handelAdd () {
      this.$store.commit('add')
    },
    handelAddN () {
      this.$store.commit('addN', 6)
    }
  }
}
</script>
