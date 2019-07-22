<template>
  <div class="hello"  >
    <form  
    v-on:submit.prevent="addToList" >
     
    <input v-model="formText" type="text">    
    </form>
 <transition-group name='list' mode="out-in">
   <TodoItem v-for="(el, index) in list" :key="index"
 :el="el"
 :id='index'
 v-on:removeItem="remove"
 />
 </transition-group>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
  components:{
    TodoItem
  },
  props: {
  },
  data(){
    return {
      list : [
        
      ],
      formText:''
    }
  },
  methods : {
    addToList(){
      this.list.push(this.formText);
      this.formText = ''
    },
    remove(removeId){
      this.list = this.list.filter(todo=> todo !== removeId.el )
    }
  }
}
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello{
  max-width: 95vw;
  margin-left: auto;
  margin-right: auto;
  margin-top: 90px;
  
}
input{
  width: 800px;
  max-width: 90vw;
  line-height: 40px;
  margin-top: 50px;
  font-size: 28px;
  margin-bottom: 30px;
}
.list-enter-active, .list-leave-active {
  transition: all .5s ease-in-out;
}
.list-enter, .list-leave-to  {
  opacity: 0;
  transform: translatey(10px)
}
</style>
