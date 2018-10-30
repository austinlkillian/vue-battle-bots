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
      <bot-list v-for='(bot, i) in botList'
      :key='i'
      :botObj='bot'/>
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
      botList: []
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
     justify-content: space-evenly;
     align-items: center;
}
</style>
