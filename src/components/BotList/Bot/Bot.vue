<template>
    <div id="bot">
            <h1>{{botObj.botName}}</h1>
            <h3>Att Val: {{botObj.attackValue}}</h3>
            <h3>HP Val: {{botObj.healthValue}}</h3>
            <div>
                <button @click="selectBot(botObj.botName)">SELECT</button>
                <button>RETIRE</button>
            </div>
        </div>
</template>

<script>
export default {
    props: ['botObj', 'selectBot']
    
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
     margin: 15px;
 }

 #bot:hover{
     background: navy;
 }
</style>
