<template>
  <li class="card" draggable="true">
        <div class="cb-container">
          <input type="checkbox" @click="confirmTask" :checked="todo.isComplete" class="cb-input" />
          <span class="check"></span>
        </div>
        <p class="item">
         <del v-if="todo.isComplete">{{todo.title}}</del> 
         <span v-else v-text="todo.title"></span>
        </p>
        <button class="clear" @click="deleteTask">
          <img src="../assets/icon-cross.svg" alt="Clear it" />
        </button>
      </li>
</template>

<script>
export default {

  methods:{
    deleteTask(){
      if(confirm("Are U Sure U Want To Delete This Task?"))
      this.$emit("TaskDeleted",this.todo.id)
    },

    confirmTask(){
      this.$emit("TaskConfirmed",this.todo.id,!this.todo.isComplete);
    }
  },

  props:{
    todo : Object
  }
}
</script>

<style>
  
</style>