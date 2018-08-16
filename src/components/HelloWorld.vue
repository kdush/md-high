<template>
  <div class="hello">
   <vue-markdown :source="mdTest" @rendered="goHigh"></vue-markdown>
  </div>
</template>

<script>
import VueMarkdown from 'vue-markdown'
import Prism from 'prismjs';

export default {
  components: {
    VueMarkdown
  },
  name: 'HelloWorld',
  data(){
    return{
      // markdown内容
      mdTest:""
    }
  },
  mounted(){
      this.mdTest='```javascript  \n console.warn(1); \n var rayzhang=\'天才\'; \n ```'
  },
  methods:{
    // 渲染结束后的事件
    goHigh(){
      Prism.highlightAll()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
// @import "../../node_modules/prismjs/themes/prism.css"; // 基本
@import "../../node_modules/prismjs/themes/prism-funky.css" // 带主题
</style>
