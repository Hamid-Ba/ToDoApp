<template>
  <AppHeader/>
  <main>
    <AddTodo @TaskAdded="TaskCreated"/>
    <ul class="todos">
      
      <AppTodo v-for="todo in todos" :key="todo.id" :todo="todo"/>

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
  
  data() {
    return {
      todos :[]
    }
  },

  methods:{
    TaskCreated(title){
      const taskId = Math.random().toString(15).slice(3);
      const newTask = {id : taskId ,title : title,isComplete : false};
      this.todos.push(newTask);
    }
  },

  components:{
    AppHeader,
    AppFooter,
    AppTodo,
    AddTodo
  }
}
</script>

<style>

</style>
