<template>
  <div id="todo-list-example">
  <form v-on:submit.prevent="addNewTodo">
    <label for="new-todo">Add a todo</label>
    <input
      v-model="newTodoText"
      id="new-todo"
      placeholder="E.g. Feed the cat"
    >
    <button>Add</button>
  </form>
  <ul>
    <li v-for="(todo, index) in todos" v-bind:key="todo.id" v-bind:style="{textDecoration: (todo.status ?'line-through':'none')}">
    <todoListItem v-bind:title="todo.title"></todoListItem>
    <button :key= "todo.title" @click = "done(index)">Changement Status</button>
    <button :key= "todo.id" @click = "suppr(index)">Supprimer</button>
    </li>
  </ul>
</div>
</template>

<script>
import todoListItem from "./todoListItem.vue"
export default {
    components:{
        todoListItem
    },
    data() {
        return{
                todos: [
 
                ],
                nextTodoId: 0,
                nextStatus: false,
                newTodoText: "",
            }
    },
    methods: {
        addNewTodo: function () {
        this.todos.push({
            id: this.nextTodoId++,
            title: this.newTodoText,
            status: this.nextStatus,
        })
        this.newTodoText = ''
        },
        
        done: function (index) {
            this.todos[index].status = !this.todos[index].status
            console.log(this.nextStatus)
        },

        suppr(index) {
            this.todos.splice(index, 1)
        }
    }

}
</script>

<style>

</style>