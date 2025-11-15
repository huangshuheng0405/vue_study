<template>
  <div class="app">
    <div v-if="isShowEdit">
      <input type="text" v-model="editValue" ref="inp" />
      <button>确认</button>
    </div>
    <div v-else>
      <span>{{ title }}</span>
      <button @click="handleEdit">编辑</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '大标题',
      isShowEdit: false,
      editValue: '',
    }
  },
  methods: {
    handleEdit() {
      // 异步dom更新
      this.isShowEdit = true
      // $nextTick 等dom更新完立即执行函数体
      this.$nextTick(() => {
        this.$refs.inp.focus()
      })
    },
  },
}
</script>

<style></style>
