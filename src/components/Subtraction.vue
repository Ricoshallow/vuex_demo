<template>
  <div>
    <h2>当前最新的count值为：{{count}}</h2>
    <button>-1</button>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {

    }
  },
  computed: {
    ...mapState(['count'])
  }
}
</script>
