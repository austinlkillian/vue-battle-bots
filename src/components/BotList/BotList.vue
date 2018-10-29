<template>
        <div>
            <h1>bot: {{botObj.botName}}</h1>
            <h3>Att Val: {{botObj.attackValue}}</h3>
            <h3>Att Val: {{botObj.healthValue}}</h3>
        </div>
</template>

<script>
export default {
    props: ['botObj'],
    
  methods: {

  }
}
</script>

<style scoped>

 #botList>div{
     display: flex;
     flex-direction: column;
     justify-content: space-evenly;
     align-items: center;
 }
</style>