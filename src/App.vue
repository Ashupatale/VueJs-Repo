<template>
<div>
<h1 :style="{color:'white', width:'50%',margin:'auto',backgroundColor:'green'}">Rendering HTML and  CSS in Vue Js</h1>
<hr/>

<h1>Hello {{name}} my Name is {{sirname}}</h1>
<div v-html="channel"></div>
<div v-html="hack" :style="{color:'red'}"></div>
<h1 :id="headingId" class="underline">Heading </h1>
<button :disabled="isDisabled" >Click here</button>
<h1 class="underline">Underline text</h1>
<h2 :class="ispromoted && 'promoted' ">Promoted movies...!</h2>
<h2 :class="isSoldOut ? 'sold-out' : 'new'">Movies Sold Out?</h2>
<h2 :class="['new', 'sold-out']">Newly Promoted movies</h2>
<h2 :style="{
  color:heighLightColor,
  fontSize:headerSize + 'px',
  padding:'20px'
}">Inline Style</h2>
<h2 :style="StyleObj">Render style as a objects</h2>

<h1 :style="{color:'white', width:'50%',margin:'auto',backgroundColor:'green'}"> Conditional Rendering in Vue Js</h1>
<hr/>
<h1 v-if="num === 0">The Number Is Zero</h1>
<h1 v-else-if="num < 0">Number is negative</h1>
<h1 v-else-if="num > 0">Number is Positive</h1>

<h1 v-else>The Number Is Not Zero...!</h1>

<h3 v-show="ShowElement">It only shows if Show If Data is true</h3>

<h1 :style="{color:'white', width:'50%',margin:'auto',backgroundColor:'green'}"> List Rendering in Vue Js</h1>
<hr/>


<h3 v-for="(name , index) in names" :key="name">Id-{{index}} Name- {{name}}</h3>

<h3 v-for="fullname in fullNames" :key="fullname">{{fullname.first}} {{fullname.last}}</h3>

<hr/>

<div v-for="actor in actors" :key="actor.name">
  <h3>{{actor.name}}</h3>
  
  <h4 v-for="movie in actor.movies" :key="movie">{{movie}}</h4>
</div>

<hr/>
<div>

   <NewApp/>


</div>
</div>
</template>


<script>
import NewApp from './components/NewApp.vue'

export default {




  name: 'App',
  components:{
    NewApp
  },
  data(){
    return{
      name : 'Batman',
      sirname:"Aakash patale",
      channel:"<i>codeEvaluation</i>",
      hack:`<a href="#" onclick="alert('You have been clicked')">Click here</a>`,
      headingId:'heading',
      isDisabled:true,
      ispromoted:true,
      isSoldOut:true,
      heighLightColor:'orange',
      headerSize:50,
      StyleObj:{
        color:'red',
        fontSize:'30px'
      },
      num:2,
      ShowElement:true,
      names:['Aakash', 'shree', 'Niraj'],
      fullNames:[
        {first:'Ashutosh' , last:'patale'},
        {first:'abc' , last:'xyz'},
        {first:'shree' , last:'abcd'}


      ],
      actors: [
        {
          name:'Yash',
          movies:['KGF', 'Masterpiece'],
        },

         {
          name:'SRK',
          movies:['Dilwale', 'DDLJ'],
        },
        
      ],
      
    }
  
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

.underline{
  text-decoration: line-through;
}
.promoted{
  font-style: italic;
}
.sold-out{
  color: red;
}

.new{
 font-style: italic;
}
</style>
