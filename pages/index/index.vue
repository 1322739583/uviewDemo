<template>
  <view class="content">
    <navigator url="/pages/upload/upload">
      <u-button text="upload"></u-button>
    </navigator>
    <navigator url="/pages/collapse/collapse">
      <u-button>collapse</u-button>
    </navigator>
    <navigator url="/pages/tabs/tabs">
      <u-button>tabs</u-button>
    </navigator>
    <navigator url="/pages/search/search">
      <u-button>search</u-button>
    </navigator>
  </view>
</template>

<script>
export default {
  data() {
    return {
      title: 'Hello'
    }
  },
  onLoad() {
    console.log(uni.$u.config.v);
  },
  methods: {}
}
</script>

<style lang="scss" scoped>

</style>
