<template>
  <div id="app">
    <header id="header">拖拽demo</header>
    <div class="parentCpt">
        <v-draggable></v-draggable>       
    </div>
  </div>
</template>

<script>
import vDraggable from './components/v-draggable.vue'
export default {
  name: 'app',
  data(){
    return{
    }
  }, 
  computed: {
  }, 
  components:{
    vDraggable
  },
  methods:{
  },
  watch: {
    isDragging (newValue) {
      console.log(123)
      if (newValue){
        this.delayedDragging= true
        return
      }
      this.$nextTick( () =>{
           this.delayedDragging =false
      })
    }
  }
}
</script>

<style>
*{margin:0;padding:0;}
body{background-color: #373c43}
#app {font-family: 'Avenir', Helvetica, Arial, sans-serif;-webkit-font-smoothing: antialiased;-moz-osx-font-smoothing: grayscale;text-align: center;color: #2c3e50;}
#header{background-color:#373c43;height:50px;color:#fff;line-height: 50px;text-align: left;padding:0 15px;}
.clear{ zoom:1;}
.clear:after{ content:''; display:block; clear:both;}
</style>
