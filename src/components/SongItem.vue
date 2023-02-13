<template>
  <van-cell
    center
    :key="id"
    :title="name"
    :label="author + ' - ' + name"
  >
    <template #right-icon>
      <van-icon name="play-circle-o" size="0.6rem" @click="playFn" />
    </template>
  </van-cell>
</template>

<script>
export default {
  props: {
    name: String,
    author: String,
    id: Number,
  },
  methods: {
    playFn(){
      this.$router.push({
        path: '/play',
        query: {
          id: this.id
        }
      })
    }
  }
};
</script>

<style scoped>
/* 给单元格设置底部边框 */
.van-cell {
  border-bottom: 1px solid lightgray;
}
</style>