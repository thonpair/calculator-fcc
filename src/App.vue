<template>
  <div id="app">
     <p id="display">{{display}}</p>
    <button v-for="number of numbers" :key="number.id" :id="number.id" v-on:click="addNum(number.title)">{{number.title}}</button>
    <button id="decimal" v-on:click="decimal">.</button>
    <button id="equals" v-on:click="equals">=</button>
    <button id="add" v-on:click="addOperator('+')">+</button>
    <button id="subtract"  v-on:click="addOperator('-')">-</button>
    <button id="multiply" v-on:click="addOperator('*')">*</button>
    <button id="divide"  v-on:click="addOperator('/')">/</button>
    <button id="clear" v-on:click="clear">C</button>

  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data(){
    return{
      numbers: [
        { id:'zero', title:'0'},
        { id:'one', title:'1'},
        { id:'two', title:'2'},
        { id:'three', title:'3'},
        { id:'four', title:'4'},
        { id:'five', title:'5'},
        { id:'six', title:'6'},
        { id:'seven', title:'7'},
        { id:'eight', title:'8'},
        { id:'nine', title:'9'},
      ],
      display: '0',
    }
  },
  
  computed:{
    evaluate : function(){
      return eval(this.display)
    }
  },
  methods:{
    addNum(num){
      if (this.display === '0'){
        this.display = '';      }
      this.display += num
    },
    addOperator(operator){
      this.display += operator
    },  
    decimal(){
      if (this.display[this.display.length -1] !== '.'){
        this.display += '.'
      }
    },
    clear(){
      this.display = '0';
    },
    equals(){
      this.display = this.evaluate;    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
