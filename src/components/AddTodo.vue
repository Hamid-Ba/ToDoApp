<template>
  <div class="card add">
      <div class="cb-container">
        <button id="add-btn" @click="addToDo">+</button>
      </div>
      <div class="txt-container">
        <Form :validation-schema = "schema">
         <label for="addt">افزودن </label>
         <Field name = "title" v-model="title"  type="text" @keypress.enter="addToDo" class="txt-input" 
           placeholder="افزودن وظیفه جدید..." spellcheck="false" 
           :validateOnInput = 'true' autocomplete="off"
           id="addt" dir="rtl" />
         <ErrorMessage name="title"  style="color:red"/>
        </Form>
        
      </div>
    </div>
</template>

<script>

import * as yup from 'yup';
import { Field, Form ,ErrorMessage} from 'vee-validate';

export default {
  components: {
    Field,
    Form,
    ErrorMessage
  },
  data(){
    const schema = yup.object({
      title : yup
        .string()
        .required("تسک خود را وارد نمایید"),
    });

    return{
      title : "",
      schema
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