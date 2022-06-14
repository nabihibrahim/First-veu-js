<template>
    <div class="it">
        <h2>IT Team</h2>
        <div v-for="(item,index) in IT" v-bind:key="index">
            <p v-if="item.department == 'IT'">
            Name: {{item.name}} 
            <button v-on:click="deleteTI(item.name)">Delete </button>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    name:'IT',
    props:['IT'],
    methods:{
        deleteTI(name){
            this.$emit('delete',{name})
        }
    }
}
</script>

<style lang="stylus">

</style>