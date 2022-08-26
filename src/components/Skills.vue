<template>
  <div class="hello">
    <div class="holder">
        <form @submit.prevent="addskill">
        <!-- <input v-validate="'required'" name="myinput" type="text">
<span>{{ errors.first('myinput') }}</span> -->
        <input type="text" placeholder="enter a skill that you have" v-model="skill" v-validate="'min:5'" name="skilll">
         <!-- v-validate="'min:5'" name="skilll"> -->
        <!-- veevalidate="'min:5'" name="skilll"> -->
        <p class="alert" v-if="errors.has('skilll')">{{error.first('skilll')}}</p>
        <input type="checkbox" id="checkbox" v-model="checked">
        </form>
         <ul>
            <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">
        <li v-for="(data,index) in skillset" :key='index'>{{data.skillset}} {{data.skill}}</li>
        </transition-group>
        <!-- We can also use {{index}}. above to show index 0,1... -->
              </ul>
        <!-- <transition name="alert in">
       
              </transition> -->
              <p>These are the skills i posses.</p>
              <!-- <div v-bind:style="{backgroundColor:bgColor,width:bgWidth,height:bgHeight}"></div> -->
              <!-- <div v-bind:class="alertObject"></div> -->
              <!-- <div v-bind:class="{alert:!showAlert,'another_class':showClass}"></div> -->
              <!-- if we put a not equal (!)the condition alert is false  -->
              <!-- <p v-if="skillset.length >=1">You have more than 1 skills</p>
              <p v-else>you have 1 or less than 1 skill</p> -->
<!-- {{name}}
{{btnState ?'The button is disabled':'The button is active'}} -->
<!-- <button v-on:click="changename" v-bind:disabled="btnState">Change name</button> -->
</div>
  </div>
</template>

<script>
export default {
  name: 'Skills',
  data()
  {
    return{
      checked:"false",
skill:'',
      // name:"hi",
      // btnState:true
      skillset:[
        {"skillset":"vue.js"},
        {"skillset":"frontEnd Developer"}, ],

        // showAlert:true,
        // showClass:true
        // alertObject:{
        //   alert:true,
        // }
        // bgColor:'yellow',
        // bgWidth:'100%',
        // bgHeight:'30px'
    }
  },
  methods:
{
  addskill()
  {
    // alert(this.skill)
    this.skillset.push({skill:this.skill})
    // alert(this.skillset)
    this.skill=''; 
    console.log('This checkbox value is'+this.checked);
     }
}
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
.holder {
    background: #fff;
  }
  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }
  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }
  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  input {
    width: calc(100% - 40px);
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: #323333;
    color: #687F7F;
  }
.alert-in-enter-active {
    animation: bounce-in .5s;
  }
  .alert-in-leave-active {
    animation: bounce-in .5s reverse;
  }
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}
</style>
