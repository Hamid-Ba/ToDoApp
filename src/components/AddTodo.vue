<template>
  <div class="card add">
      <div class="cb-container">
        <button id="add-btn" @click="addToDo">+</button>
      </div>
      <div class="txt-container">
        <label for="addt">افزودن </label>
        <input v-model="title" type="text" @keypress.enter="addToDo" class="txt-input" 
        placeholder="افزودن وظیفه جدید..." spellcheck="false" autocomplete="off"
          id="addt" dir="rtl" />
      </div>
    </div>
</template>

<script>
export default {
  data(){
    return{
      title : ""
    }
  },
  methods : {
    addToDo(){
      if(this.title.trim().length !== 0)
      this.$emit("TaskAdded",this.title);
      this.title = "";
    }
  }
}
</script>

<style>

</style>