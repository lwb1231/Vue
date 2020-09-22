<template>
    <div>
      <head-com></head-com>
        我是关于页
      <button @click='goHome'>去首页</button>
      <div>
        <button @click='add'>点击获取</button>
        <button @click='up'>点击修改</button>
      </div>
    </div>
</template>
<script>
import headCom from '../../components/headerCom'

export default{
  name: 'about',
  components: {
    headCom
  },
  mounted () {
    var name2 = this.$route.params.name
    console.log(name2)
  },
  methods: {
    add () {
      console.log(this.$store.state.count)
    },
    up () {
      this.$store.commit('increment')
    },
    goHome () {
      this.$router.push({path: '/home?id=' + 123})
      // this.$router.push({path: '/home', query: [id, 123]})
    }
  }
}
</script>
<style scoped>

</style>
