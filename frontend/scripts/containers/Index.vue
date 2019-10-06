<template lang="pug">
#app
  .wrapper.columns.is-centered
    .column.is-half
      nav.panel
        TaskHead
        TaskInput(@add="add")
        TaskItem(v-for="(todo, index) in todos" :todo="todo.name", :index="index", :checked="todo.checked" @del = "del" @check = "check")
        TaskFoot(@rchecked="rchecked")

</template>
<script lang="ts">
import TaskHead from 'scripts/components/TaskHead.vue'
import TaskItem from 'scripts/components/TaskItem.vue'
import TaskInput from 'scripts/components/TaskInput.vue'
import TaskFoot from 'scripts/components/TaskFoot.vue'
export default {
  name: 'Index',
  data () {return {
    todos: [{name: "a", checked: false}, {name: "b", checked: false}, {name: "c", checked: false}]
  }},
  components: {
    TaskHead,
    TaskItem,
    TaskInput,
    TaskFoot,
  },
  methods: {
    del (index: number){
        this.todos.splice(index, 1);
    },
    check (index: number){
        this.todos[index].checked = !this.todos[index].checked
    },
    rchecked (){
        for(var i = 0;i < this.todos.length;i++){
            if (this.todos[i].checked == true){
                this.todos.splice(i, 1);
                i--
            }
        }
    },
    add (t: string){
        this.todos.push({name: t, checked: false})
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