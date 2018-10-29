<template>
    <div id="create">
        <div>
            <h3>Bot Name*</h3>
            <input v-model='botName' type="text">
        </div>

        <div>
            <h3>Attack Value*</h3>
            <input v-model='attackValue' type="text">
        </div>

        <div>
            <h3>Health Value*</h3>
            <input v-model='healthValue' type="text">
        </div>
        <div id='buttons'>
            <button @click='addBot({botName, attackValue, healthValue})'>SUBMIT</button>
            <button @click='clear'>CLEAR</button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['addBot'],

data() {
    return {
        botName: '',
        attackValue: 0,
        healthValue: 0
    }
  },
  methods: {
      clear(){
      this.botName = '';
      this.attackValue = 0;
      this.healthValue = 0;
    }
  }
}
</script>

<style scoped>
 #create{
     width: 400px;
     height: 400px;
     background: white;
     display: flex;
     flex-direction: column;
     justify-content: space-evenly;
     align-items: center;
     position: relative;
     top: 20px;
     border-radius: 7px;
 }

 #create>input{
     width: 300px;
     height: 30px;
 }

 #buttons{
     width: 100%;
     display: flex;
     justify-content: space-evenly;
 }
</style>

