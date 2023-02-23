<template>
  <view>
    <u-collapse
        @change="change"
        @close="close"
        @open="open"
    >
      <u-collapse-item title="成员列表" name="Docs guide">
        <u-list @scrolltolower="scrolltolower">
          <u-list-item v-for="(item, index) in indexList" :key="index">
            <u-cell
                :title="`列表长度-${index + 1}`"
            >
              <u-avatar
                  slot="icon"
                  shape="square"
                  size="35"
                  :src="item.url"
                  customStyle="margin: -3px 5px -3px 0"
              ></u-avatar>
            </u-cell>
          </u-list-item>
        </u-list>
      </u-collapse-item>
      <u-collapse-item
          title="组件全面"
          name="Variety components"
      >
        <text class="u-collapse-content">众多组件覆盖开发过程的各个需求，组件功能丰富，多端兼容。让您快速集成，开箱即用
        </text>
      </u-collapse-item>
    </u-collapse>
  </view>
</template>

<script>
export default {
  data() {
    return {
      indexList: [],
      urls: [
        'https://cdn.uviewui.com/uview/album/1.jpg',
        'https://cdn.uviewui.com/uview/album/2.jpg',
        'https://cdn.uviewui.com/uview/album/3.jpg',
        'https://cdn.uviewui.com/uview/album/4.jpg',
        'https://cdn.uviewui.com/uview/album/5.jpg',
        'https://cdn.uviewui.com/uview/album/6.jpg',
        'https://cdn.uviewui.com/uview/album/7.jpg',
        'https://cdn.uviewui.com/uview/album/8.jpg',
        'https://cdn.uviewui.com/uview/album/9.jpg',
        'https://cdn.uviewui.com/uview/album/10.jpg',
      ]
    }
  },
  onLoad() {
    this.loadmore()
  },
  methods: {
    open(e) {
      // console.log('open', e)
    },
    close(e) {
      // console.log('close', e)
    },
    change(e) {
      // console.log('change', e)
    },
    scrolltolower() {
      this.loadmore()
    },
    loadmore() {
      for (let i = 0; i < 30; i++) {
        this.indexList.push({
          url: this.urls[uni.$u.random(0, this.urls.length - 1)]
        })
      }
    }
  }
}
</script>

<style scoped>

</style>