<template>
  <div class="hello">
    <vue-markdown :source="mdTest" @rendered="goHigh"></vue-markdown>
  </div>
</template>

<script>
import VueMarkdown from 'vue-markdown'
import Prism from 'prismjs';
import mdText from './py'
export default {
  components: {
    VueMarkdown
  },
  name: 'HelloWorld',
  data () {
    return {
      // markdown内容
      mdTest: ""
    }
  },
  mounted () {
    this.mdTest = mdText
  },
  methods: {
    // 渲染结束后的事件
    goHigh () {
      console.debug(Prism)
      Prism.highlightAll()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
// @import "../../node_modules/prismjs/themes/prism.css"; // 基本
@import "../../node_modules/prismjs/themes/prism-dark.css";
</style>
