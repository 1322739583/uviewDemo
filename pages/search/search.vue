<template>
  <view>
    <u-search placeholder="日照香炉生紫烟" v-model="keyword"></u-search>
    <u-search :showAction="true" actionText="搜索" :animation="true"></u-search>
    <u-search shape="square"></u-search>
    <u-search :clearabled="true"></u-search>
    <u-search inputAlign="center" height="70"></u-search>
  </view>
</template>

<script>
export default {
  data() {
    return {
      keyword: '遥看瀑布挂前川'
    }
  },
  methods: {

  }
}
</script>

<style scoped>

</style>