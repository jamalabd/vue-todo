<!-- Todo list  -->
<!-- 
  create data for todo ✅
  Create todo template (html) ✅
  CRUD operations for todo's
    - create new todo
        - input control ✅
        - update state with input data ✅
          - form submission ✅
            - prevent default action ✅
            - create new action to add to the array on submit ✅
    - read todo's ✅
    - update todo 
      - update todo isnt working properly
      - save todo isnt working properly
    - delete todo ✅ 
--> 
<script setup>
import {ref} from 'vue'

// create the data or fetch the data
const todos = ref([{todo: 'My to da loo'}]);
const newTodo = ref(''); 
const editedTodo = ref(''); 
const editing = ref(false);
// function handling submit
const addTodo = ()=>{
  if(newTodo.value){
    todos.value.push({
      todo: newTodo.value
    })
    newTodo.value = '';
  }
}

const editTodo =(index)=> {
    editing.value = true;
    todos.value[index].todo = editedTodo;
}

const saveTodo =()=> {
    editing.value = false;
}

const deleteTodo = (index)=>{
   todos.value = todos.value.filter((todo, indexofTodo) => indexofTodo !== index); 
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
        <li v-for="(item, index) in todos" class="todoItem">
          <p>{{ item.todo }}</p>
          <label for="editTodo">
      </label>
      <input type="text" v-model="editedTodo" v-if="editing" name="editTodo" id="editTodo">
          <button @click="editTodo(index)"> Edit </button><button @click="saveTodo()" v-if="editing"> Save </button><button @click="deleteTodo(index)"> Delete </button>
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
