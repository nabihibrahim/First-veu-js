<template>
    <div>
        <h1>{{Message}}</h1>
        <h1>{{Message2}}</h1>
    </div>
</template>

<script>
export default {
    name: 'AppTest',
    data(){
        return{
            Message : 'Hello Guys from test component',
            Message2 : 'أهلا بكم يا أصدقاء'
        }
    }
}
</script>

<style>

</style>