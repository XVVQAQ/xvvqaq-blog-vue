<script>
import "@/router/index.js"
export default {
  data(){
    return {
      top:"",
      navShow:false
    }
  },
  mounted() {
    window.addEventListener("scroll", ()=>{
      this.top = document.documentElement.scrollTop||
         document.body.scrollTop||
          window.pageYOffset;
    })
  },
  watch: {
    top(newVal,oldVal){
      if(newVal>20){
        if(newVal>oldVal){
          this.navShow=false;
        }else if(newVal<oldVal){
          this.navShow=true;
        }
      }
    }
  }
}

</script>

<template>
  <nav :class="navShow ? 'navOn' : 'navOff'">
    <RouterLink to="/">Go to Home</RouterLink>
    <RouterLink to="/about">Go to About</RouterLink>
    <RouterView />
  </nav>

</template>

<style scoped>
.navOn{
  position: fixed;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
</style>