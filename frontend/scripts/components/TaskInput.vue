<template lang="pug">
.task-input.panel-block
  .field.has-addons
    .control
      input.input(type="text" v-model="t")
    .control
      button.button.is-primary(@click="add") 追加
</template>

<script lang="ts">
import TaskItem from 'scripts/components/TaskItem.vue'

export default {
  name: 'Index',
  data(){return {
    t: ""
    }},
  components: {
    TaskItem,
  },
  methods: {
    add (){
      this.$emit('add', this.t)
      this.t = ""
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'styles/main/vue'
#app
  height: 100vh
  .wrapper
    display: flex
    align-items: center
    height: 100%
</style>
