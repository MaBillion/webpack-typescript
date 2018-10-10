<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <section>
      <ul>
        <li><input @click="_onClick" type="radio" name="radio"><span>radio1</span></li>
        <li><input type="radio" name="radio"><span>radio2</span></li>
        <li><input type="radio" name="radio"><span>radio3</span></li>
        <li><input type="radio" name="radio"><span>radio4</span></li>
        <li><input type="radio" name="radio"><span>radio5</span></li>
        <li><span>{{str1}}</span></li>
      </ul>
    </section>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg: string;
  
  str1: string = '123'
  
  _onClick (e): void {
     let con = window.confirm()
      if (con) {
      } else {
          e.preventDefault()
      }
  }
  
  // 生命周期
  created () {
      console.log(this.str1) // 全局变量
  }
  
  mounted () {
      console.log(this) // vue 组件实例
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
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
