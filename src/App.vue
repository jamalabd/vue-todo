<!-- Todo list  -->
<!-- 
  create data for todo ✅
  Create todo template (html) ✅
  CRUD operations for todo's
    - create new todo
        - input control ✅
        - update state with input data ✅
          - form submission
            - prevent default action
            - create new action to add to the array on submit
    - read todo's
    - update todo
    - delete todo 
--> 
<script setup>
import {ref} from 'vue'

// create the data or fetch the data
const todos = ref([{todo: 'My to da loo'}]);
const newTodo = ref(''); 
// function handling submit
const addTodo = ()=>{
  if(newTodo.value){
    todos.value.push({
      todo: newTodo.value
    })
    newTodo.value = '';
  }
}

</script>

<template>
  <main>
    <div class="todo">
      <h1> My Todo's</h1>
      <form @submit.prevent="addTodo">
      <label for="search">
      </label>
      <input type="text" v-model="newTodo" name="search" id="search">
      <button type="submit" class="searchBtn"> Save </button>
      </form>
      <ul id="todoList">
        <li v-for="item in todos" class="todoItem">
          <p>{{ item.todo }}</p>
      </li>
      </ul>
  </div>
  </main>
</template>

<style scoped>
body {
  padding: 5rem;
  background-color: black;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

.todo {
    width: 100%;
  }

#todoList {
    list-style-type: none;
  }

  #search {
    margin: 1rem 0;
    width: 90%;
    height: 100%;
  }
  .searchBtn {
  }

</style>
