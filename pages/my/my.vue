<template>
  <view>
    <!-- 用户未登录时 -->
    <my-login v-if="!token"></my-login>
    <!-- 用户登陆后 -->
    <my-userinfo v-else></my-userinfo>
  </view>
</template>

<script>
  // 导入自己封装的 mixin 模块
  import badgeMix from '@/mixins/tabbar-badge.js'
  // 从 vuex 中按需导入 mapstate 辅助函数
  import { mapState } from 'vuex'

  export default {
    // 将 badgeMix 混入到当前的页面中进行使用
      mixins: [badgeMix],
    data() {
      return {
        
      };
    },
    computed: {
      // 从 m_user 模块中导入需要的 token 字符串
      ...mapState('m_user', ['token'])
    },
  }
</script>

<style lang="scss">

</style>
