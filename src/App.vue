<template>
  <AppHeader/>
  <main>
    <AddTodo/>
    <ul class="todos">

      <AppTodo/>
      <AppTodo/>
      <AppTodo/>      
      
    </ul>
    <div class="card stat">
      <p class="corner"><span id="items-left">0</span> مورد باقی مانده</p>
      <div class="filter">
        <button id="all" class="on">همه</button>
        <button id="active" >فعال</button>
        <button id="completed">تکمیل</button>
      </div>
      <div class="corner">
        <button id="clear-completed">حذف تکمیل شده ها</button>
      </div>
    </div>
  </main>
  <AppFooter />
</template>

<script>
import AppHeader from "./components/AppHeader.vue"
import AppFooter from "./components/AppFooter.vue"
import AppTodo from "./components/AppTodo.vue"
import AddTodo from "./components/AddTodo.vue"
export default {
  name: 'App',
  
  components:{
    AppHeader,
    AppFooter,
    AppTodo,
    AddTodo
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
