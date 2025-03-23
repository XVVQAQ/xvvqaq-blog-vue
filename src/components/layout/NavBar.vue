<script>
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

  </nav>
</template>

<style scoped>

</style>