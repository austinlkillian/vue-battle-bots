<template>
  <div id="app">
    <header>
      <button @click='switchView(true)'>CREATE</button>
      <h1>Battle Bots</h1>
      <button @click='switchView(false)'>COLLECTION</button>
    </header>

    <section v-if='showForm'>
      <create 
        :addBot='addBot'
        />
    </section>

    <section id='bot-list' v-else>
      <div>
        <h1>BOT #1: {{bot1 ? bot1.botName : 'select a bot'}}</h1>
        <h1>BOT #2: {{bot2 ? bot2.botName : 'select a bot'}}</h1>
        <div>
            <button @click='battle' :disabled='this.bot1 && this.bot2 ? false : true'>BATTLE</button>
            <button @click="clearBots">CLEAR</button>
        </div>
      </div>
      <div id='bots'>
        <bot-list v-for='(bot, i) in botList'
        :key='i'
        :botObj='bot'
        :selectBot='selectBot'
        :clearBots='clearBots'/>
      </div>
    </section>
  </div>
</template>

<script>
import Create from './components/Create'
import BotList from './components/BotList/BotList'

export default {
  data() {
    return {
      showForm: true,
      botList: [
        {botName: 'Elaine', attackValue: 30, healthValue: 20},
        {botName: 'George', attackValue: 40, healthValue: 10},
        {botName: 'Jerry', attackValue: 10, healthValue: 40}
      ],
      bot1: '',
      bot2:''
    }
  },
  methods: {
    switchView(val) {
      this.showForm = val
    },
    addBot(newBot){
      this.botList.push({
        botName: newBot.botName,
        attackValue: newBot.attackValue,
        healthValue: newBot.healthValue
      })
      this.botName = '';
      this.attackValue = 0;
      this.healthValue = 0;
      this.switchView(false);
    },
    selectBot(bot){
      if(!this.bot1){
        this.bot1 = bot
        return;
      }else if(!this.bot2){
        this.bot2 = bot
        return;
      }
    },
    clearBots(){
      this.bot1 = ''
      this.bot2 = ''
      return;
    }, 
    battle(){
      let battleList = [this.bot1, this.bot2]
      let winner = battleList[Math.floor(Math.random() * battleList.length)]
      alert(`By random choice, ${winner.botName} has won!`)
    }
  },
  components: {
    Create,
    BotList
  }
}
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: rgb(10, 255, 112);
  height: 98vh;
  width: 98vw;
}

header{
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 100%;
  height: 120px;
  background: navy;
}

#bot-list{
     width: 100%;
     display: flex;
     flex-direction: column;
     justify-content: space-evenly;
     align-items: center;
}

#bots{
        display: flex;
        justify-content: space-evenly;
        align-items: center;
    }
</style>
