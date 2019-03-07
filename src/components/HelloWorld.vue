<template>
  <div class="hello">
    <h1>{{ this.currentCity}}</h1>
    <h2>{{this.city}}</h2>
    <test :name.sync="msg"></test>

    
  </div>
</template>

<script>
  import {mapState,mapGetters} from "vuex"
  import test from "./test.vue"
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components:{
    test,
  },
  computed:{
    ...mapState(['city']),
    ...mapGetters(['currentCity'])
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
