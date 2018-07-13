<template>
  <div id="app">
    <img :src="img">
    <router-view></router-view>
  </div>
</template>

<script>
import Mock from 'mockjs'

export default {
  name: 'app',
  data(){
    return {
      img:''
    }
  },
  mounted(){
    var data = Mock.mock({
        'list|1-10': [{
            'id|+1': 1,
            'isOk|1' : true,
            'name|2-33' : /\w/,
            'color' : Mock.Random.color(),
            'email' : Mock.Random.email()
        }]
    })
    console.log(JSON.stringify(data, null, 4),Mock.Random.date('yyyy-MM-dd HH:mm:ss'));
    this.img = Mock.Random.image('200x100', '#894FC4', '#FFF', 'png', '!');
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
