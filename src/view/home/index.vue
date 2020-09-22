<template>
    <div>
        <head-com :obj='obj' @msg='getMsg'></head-com>
        我是首页
        <button @click='goAbout'>去关于</button>
        <router-link to="./login">去登陆</router-link>
        <div class="box">
            <p>ssss</p>
            <span>dddd</span>
            <h5>lalla <span>eeee</span></h5>
        </div>
    </div>
</template>
<script>
import headCom from '../../components/headerCom'

export default{
  data () {
    return {
      obj: '我是父组件'
    }
  },
  name: 'home',
  components: {
    headCom
  },
  mounted () {
    console.log(this.$route.query.id)
    console.log(this.$store.state.count)
  },
  methods: {
    goAbout () {
      this.$router.push({name: 'About', params: {name: '123'}})
    },
    getMsg (val) {
      console.log(val)
    }
  }
}
</script>
<style scoped lang="scss">
$height:20px;
$c:red;
$b:blue;
$y:yellow;
.box{
    height: $height;
    p{
        color: $c;
    }
    span{
        color: $b;
    }
    h5{
        color: $y;
        span{
            color: $b;
        }

    }
}

</style>
