<template lang="pug">
.task-foot.panel-block
  button.button.is-danger(@click="rchecked") チェックしたタスクを削除
</template>

<script lang="ts">
export default {
  name: 'TaskFoot',
  methods: {
    rchecked () {
        this.$emit('rchecked')
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'styles/main/vue'
</style>
