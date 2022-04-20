<template>
   <header class="card">
    <h1>لیست وظایف </h1>
    
    <button id="theme-switcher">
      <img :src="icon" @click="ChangeTheme" alt="Change color theme" />
    </button>
  </header>
</template>

<script>
  import SunIcon from "../assets/icon-sun.svg";
  import MoonIcon from "../assets/icon-moon.svg";

export default {
  data() {
    return {
      icon : SunIcon
    }
  },

  methods: {
    ChangeTheme(){
      if(this.icon == SunIcon)
      {
        this.icon = MoonIcon;
        document.querySelector("body").classList.add('light')
      }
      else 
      {
        this.icon = SunIcon;
        document.querySelector("body").classList.remove('light')
      }
    }
  },
}
</script>

<style>

</style>