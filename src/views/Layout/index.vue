<template>
  <div>
    <van-nav-bar :title="activeTitle" fixed />
    <!-- 二级路由挂载点 -->
    <div class="main">
    <router-view></router-view>
    </div>
    <van-tabbar route>
      <van-tabbar-item replace to="/layout/home" icon="home-o">首页</van-tabbar-item>
      <van-tabbar-item replace to="/layout/search" icon="search">搜索</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTitle: this.$route.meta.title, // "默认"顶部导航要显示的标题 (默认获取当前路由对象里的meta中title值)

    };
  },
    // 路由切换 - 侦听$route对象改变
  watch: {
    $route(){
      this.activeTitle = this.$route.meta.title; // 提取切换后路由信息对象里的title显示
    }
  }
};
</script>

<style scoped>
.main {
  padding-top: 46px;
  padding-bottom: 50px;
}
</style>