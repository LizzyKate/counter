<template>
  <div class="container">
  <div class="row max-height align-items-center">
   <div class="col-10 mx-auto col-md-6 text-center main-container p-5">
    <h1 class="text-uppercase">counter</h1>
    <h1 ref="change">{{counter}}</h1>
    <div class="btn-container d-flex justify-content-around flex-wrap">
     <button class="btn counterBtn prevBtn text-uppercase m-2" v-on:click="subtract()">lower count</button>
     <button class="btn counterBtn nextBtn text-uppercase m-2" v-on:click="add()">add count</button>
    </div>
   </div>
  </div>
 </div>
</template>

<script>
import  './assets/css/main.css';
export default {
  data () {
    return {
     counter:0
    }
  },
  methods:{
    add(){
      this.counter++;
      if(this.counter > 0){
      this.$refs.change.style.color= 'red'
      }
    },
    subtract(){
      this.counter--;
      if(this.counter < 0){
      this.$refs.change.style.color= 'green'
      }
    }
  }
}
</script>

<style>
:root {
  --mainWhite: #f5f5f5;
  --mainGreen: #7fb800;
  --mainBlue: #0d2c54;
  --lightBlue: #00a6ed;
  --mainBlack: #333333;
}
.max-height {
  min-height: 100vh;
}
.main-container {
  border: 0.1rem solid var(--mainWhite);
  box-shadow: 0 0.5rem 0.5rem rgba(0, 0, 0, 0.9);
  border-radius: 0.2rem;
}
#counter {
  color: var(--mainGreen);
  font-size: 10rem;
  color: var(--mainBlack);
}
.prevBtn,
.nextBtn {
  box-shadow: 0 0.2rem 0.5rem rgba(0, 0, 0, 0.9);
  background: var(--mainBlue);
  color: var(--mainWhite);
}
.prevBtn:hover {
  background: var(--lightBlue);
}
.nextBtn:hover {
  background: var(--lightBlue);
}
</style>
