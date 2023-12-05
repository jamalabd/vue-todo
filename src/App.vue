<!-- Todo list  -->
<!-- 
  Create todo
  display todo's
  delete todo's
-->
<script setup>
import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <div class="todoList">
      <h1> My Todo's</h1>
      <form>
      <label for="search">
      </label>
      <input type="text" name="search" id="search">
      <button class="searchBtn"> Save </button>
      </form>
  </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  main {
    height: 100vh;
    padding: 5rem;
    box-shadow:black;
    text-align: center;
  }
  .todoList {
    width: 100%;
  }
  #search {
    margin: 1rem 0;
    width: 90%;
    height: 100%;
  }
  .searchBtn {

  }

}
</style>
