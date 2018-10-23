<template>
  <div>
    <h1>Todo Example</h1>
    <form v-on:submit.prevent="addNewTodo">
      <label for="new-todo">Add new todo</label>
      <input 
        type="text" 
        v-model="todoInput"
        palceholder="Add a todo"
      >
      <button>Add</button>
    </form>
    <u>
      <li
        is="todoItem"
        v-for="(todo, index) in todos"
        :key="todo.id"
        v-bind:text="todo.text"
        v-bind:id="todo.id"
        v-on:remove="todos.splice(index,1)"
      >
      </li>
    </u>
  </div>
</template>

<script>
  import todoItem from './common/todo-item';

  export default {
    components: {
      todoItem
    },
    data() {
      return {
        todoInput: '',
        todos: [
          {id: 1, text: 'Todo 1'},
          {id: 2, text: 'Todo 2'}
        ],
        nextTodoId: 3
      }
    },

    methods: {
      addNewTodo: function () {
        this.todos.push({
          id: this.nextTodoId++,
          text: this.todoInput
        });
        this.todoInput = '';
      }
    }
  }
</script>
