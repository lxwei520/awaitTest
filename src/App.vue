<template>
    <div id="app">
    </div>
</template>

<script>

  let test = async A => {
    console.log("start ")
    A().then(n => {
      console.log(n)
    })

   await createPromise();


    console.log("end ")
  }

  let funcA = async () => {
    console.log("a1")

    new Promise(resolve=> {
      console.log("a4")
      resolve()
    }).then(()=>{
      console.log("a5")
    })


    return 8;
  }

  let createPromise = ()=>{
    return new Promise(resolve => {
        console.log("a3")
        resolve(9)
    })
  }

  export default {
    name: 'app',
    created(){
      this.init()
    },
    methods:{
      init(){
        test(funcA)
      }
    }
  }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
