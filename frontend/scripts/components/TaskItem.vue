<template lang="pug">
.task-item.panel-block
  input(type="checkbox" v-model="checked" @click="check")
  | {{todo}}
  button.button.is-danger.is-small.is-outlined(type="button" @click="del") 削除
</template>

<script lang="ts">
export default {
  name: 'TaskItem',
  props: {
    todo: String,
    checked: Boolean,
    index: Number
  },
  methods: {
    del(){
        this.$emit('del', this.index)
    },
    check(){
        this.$emit('check', this.index)
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'styles/main/vue'
</style>
