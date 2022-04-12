<template>
  <header class="card">
    <h1>لیست وظایف </h1>
    
    <button id="theme-switcher">
      <img src="./assets/icon-sun.svg" alt="Change color theme" />
    </button>
  </header>
  <main>
    <div class="card add">
      <div class="cb-container">
        <button id="add-btn">+</button>
      </div>
      <div class="txt-container">
        <label for="addt">افزودن </label>
        <input type="text" class="txt-input" placeholder="افزودن وظیفه جدید..." spellcheck="false" autocomplete="off"
          id="addt" dir="rtl" />
      </div>
    </div>
    <ul class="todos">

      <li class="card" draggable="true">
        <div class="cb-container">
          <input type="checkbox" class="cb-input" />
          <span class="check"></span>
        </div>
        <p class="item">یادگیری جاوااسکریپت</p>
        <button class="clear">
          <img src="./assets/icon-cross.svg" alt="Clear it" />
        </button>
      </li>


      
      <li class="card" >
        <div class="cb-container">
          <input type="checkbox" class="cb-input" />
          <span class="check"></span>
        </div>
        <p class="item">یادگیری Nodejs</p>
        <button class="clear">
          <img src="./assets/icon-cross.svg" alt="Clear it" />
        </button>
      </li>
      
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
  <footer>
    <p> برای مرتب کردن وظایف میتوانید وظیفه موردنظر را بکشید و رها کنید - Drag And Drop</p>
  </footer>
</template>

<script>

export default {
  name: 'App',
  
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
