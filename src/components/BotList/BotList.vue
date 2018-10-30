<template>
        <div id="bot">
            <h1>bot: {{botObj.botName}}</h1>
            <h3>Att Val: {{botObj.attackValue}}</h3>
            <h3>Att Val: {{botObj.healthValue}}</h3>
        </div>
</template>

<script>
export default {
    props: ['botObj'],
    data() {
        return {
            bot1: {},
            bot2: {}
        }
    },
    methods: {

    }
}
</script>

<style scoped>

 #bot{
     width: 200px;
     height: 300px;
     display: flex;
     flex-direction: column;
     justify-content: space-evenly;
     align-items: center;
     background: blue;
 }

 #bot:hover{
     background: navy;
 }
</style>