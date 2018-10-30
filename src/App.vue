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
        <h1>BOT #1: {{bot1 ? bot1 : 'select a bot'}}</h1>
        <h1>BOT #2: {{bot2 ? bot2 : 'select a bot'}}</h1>
        <div>
            <button>BATTLE</button>
            <button>CLEAR</button>
        </div>
      </div>
      <div id='bots'>
        <bot-list v-for='(bot, i) in botList'
        :key='i'
        :botObj='bot'/>
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
      botList: [],
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
