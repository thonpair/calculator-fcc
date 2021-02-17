<template>
  <div id="app">
     <p id="display">{{display}}</p>
     <div id="padNum">

    <div class="button" id="one"  v-on:click="addNum('1')">1</div>
    <div class="button" id="two"  v-on:click="addNum('2')">2</div>
    <div class="button" id="three"  v-on:click="addNum('3')">3</div>
    <div class="button" id="four"  v-on:click="addNum('4')">4</div>
    <div class="button" id="five"  v-on:click="addNum('5')">5</div>
    <div class="button" id="six"  v-on:click="addNum('6')">6</div>
    <div class="button" id="seven"  v-on:click="addNum('7')">7</div>
    <div class="button" id="eight"  v-on:click="addNum('8')">8</div>
    <div class="button" id="nine"  v-on:click="addNum('9')">9</div>
    <div class="button" id="zero"  v-on:click="addNum('0')">0</div>
    <div class="button" id="decimal" v-on:click="decimal">.</div>

<div class="button" id="clear" v-on:click="clear">C</div>
    <div class="button" id="add" v-on:click="addOperator('+')">+</div>
    <div class="button" id="subtract"  v-on:click="addOperator('-')">-</div>
    <div class="button" id="multiply" v-on:click="addOperator('*')">*</div>
    <div class="button" id="divide"  v-on:click="addOperator('/')">/</div>

    
        <div class="button double"  id="equals" v-on:click="equals">=</div>
</div>
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
  font-family: 'PT Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 300px;
  margin: auto;

}

#display{
  background-color: rgb(24, 23, 23);
  color:antiquewhite;
  text-align: end;
  width: 250px;
  padding: 20px;
  height: 34px;
  margin-left: 5px;
  margin-bottom: 2px;
  font-size: 30px;
}

.button{
  display: inline-block;
  width: 95px;
  padding-top: 20px;
  padding-bottom: 20px;
  background-color: darkslategrey;
  color: white;
  margin:1px
}

.button:hover{
  background-color:darkgoldenrod;
}

.double{
  width:192px;
}
</style>
