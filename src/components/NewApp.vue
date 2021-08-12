<template>
<h1 :style="{color:'white', width:'50%',margin:'auto',backgroundColor:'green'}"> Adding Methods in Vue Js</h1>
<hr/>

    <h2>Addition - {{add(2,9,6 )}}</h2>
    <h2>Multiplication {{multiply(10)}}</h2>
</template>

<script>
export default {

    name:'NewApp',
    data(){
        return {
            baseMultiplier:5
        }
    },

    methods:{
        shuffle(){
            console.log(this.InputNames)
        },

        add(a,b,c){
            return a+b+c
        },
        multiply(num){
            return num * this.baseMultiplier
        }
    }



}
</script>