<template>
  <div class="cubes-page" :class="type">
    <header class="header">
      <h1>{{title}}</h1>
      <i @click="back" class="cubesic-back icon iconfont">&#xe624;</i>
    </header>
    <div class="wrapper">
      <section v-show="desc" class="desc">
      	<slot name="desc">{{desc}}</slot>
      </section>
      <main class="cubes-page-content">
        <slot name="content">{{content}}</slot>
      </main>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      title: {
        type: String,
        default: '',
        required: true
      },
      type: {
        type: String,
        default: ''
      },
      desc: {
        type: String,
        default: ''
      },
      content: {
        type: String,
        default: ''
      }
    },
    methods: {
      back() {
        this.$router.back();
      }
    }
  }
</script>

<style lang="less">
  @import '../../static/style/page.less';		
</style>