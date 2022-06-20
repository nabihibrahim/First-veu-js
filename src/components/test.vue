<template>
    <div>
        <h1>{{Message}}</h1>
        <h1>{{Message2}}</h1>

        <div class="post" v-for="(post,id) in posts" :key="id">
            <h3>{{post.title}}</h3>
            <p>{{post.body}}</p>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'AppTest',
    data(){
        return{
            Message : 'Hello Guys from test component',
            Message2 : 'أهلا بكم يا أصدقاء',
            posts:[]
        }
    },
  async created(){
        // alert('Created')
      await  axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(res=>{
            this.posts = res.data
        }).catch(e=>{
            console.log(e)
        })
    },
    beforeCreate() {
        alert('beforeCreate')
    },
}
</script>

<style>

</style>