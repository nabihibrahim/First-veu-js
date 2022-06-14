<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <AppTest  />
  <HRdep :HR="employees" @delete="deleteEmployee"/>
  <ITdep :IT="employees" @delete="deleteEmployee"/>

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import AppTest from './components/test.vue'
import HRdep from './components/HR.vue'
import ITdep from './components/IT.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    AppTest,
    HRdep,
    ITdep
  },
  data(){
    
        return{
            employees:[
                {name:'Nabih Ibrahim', age:30, department:'HR'},
                {name:'Medo Ibrahim', age:23, department:'HR'},
                {name:'Eman Ibrahim', age:28, department:'HR'},
                {name:'Ahmed Ibrahim', age:26, department:'IT'},
                {name:'mhmd Ibrahim', age:30, department:'IT'}
            ]
        }
        
    },
    methods:{
      deleteEmployee(name){
        // this.employees.splice(name,1)
        this.employees = this.employees.filter(employee =>{
          return employee.name != name.name 
        })
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
</style>
