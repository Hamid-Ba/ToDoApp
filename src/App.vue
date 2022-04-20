<template>
  <AppHeader/>
  <main>
    <AddTodo @TaskAdded="TaskCreated"/>
    <ul class="todos">
      
      <AppTodo v-for="(todo,index) in todos" :key="todo.id" :todo="todo"
       @TaskDeleted="DeleteTask"
       @TaskConfirmed="ConfirmTask"
       @dragover.prevent
       @dragstart="FillDragIndex(index)"
       @drop="DropItem(index)" />

    </ul>
    <div class="card stat">
      <p class="corner"><span id="items-left">{{remainTask}}</span> مورد باقی مانده</p>
      <div class="filter">
        <button id="all" class="on">همه</button>
        <button id="active" >فعال</button>
        <button id="completed">تکمیل</button>
      </div>
      <div class="corner">
        <button id="clear-completed" @click="RemoveCompleted">حذف تکمیل شده ها</button>
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
      todos :[],
      dragIndex : -1
    }
  },

  computed:{
    remainTask(){
      return this.todos.filter(t => !t.isComplete).length
    }
  },

  methods:{

    TaskCreated(title){
      const taskId = Math.random().toString(15).slice(3);
      const newTask = {id : taskId ,title : title,isComplete : false};
      this.todos.push(newTask);
    },

    DeleteTask(id){
      var newTodos = [...this.todos];
      newTodos = newTodos.filter(t => t.id !== id);
      this.todos = newTodos;
    },

    ConfirmTask(id,newStatus){
      var newTodos = [...this.todos];
      var task = newTodos.find(t => t.id === id);
      task.isComplete = newStatus;
    },

    RemoveCompleted(){
      if(confirm("Are U Sure U Want To Clear Completed ?"))
         this.todos = this.todos.filter(t => !t.isComplete);
    },

    FillDragIndex(index){
      this.dragIndex = index;
    },

    DropItem(index){
      var dragedElement = this.todos.splice(this.dragIndex,1)[0];
      this.todos.splice(index,0,dragedElement)
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