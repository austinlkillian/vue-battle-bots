<template>
    <div>
        <!-- <div>
            <h1>BOT #1: {{bot1 ? bot1 : 'select a bot'}}</h1>
            <h1>BOT #2: {{bot2 ? bot2 : 'select a bot'}}</h1>
            <div>
                <button>BATTLE</button>
                <button>CLEAR</button>
            </div>
        </div> -->
        <bot :botObj='botObj'/>
        <!-- <div id="bot">
            <h1>bot: {{botObj.botName}}</h1>
            <h3>Att Val: {{botObj.attackValue}}</h3>
            <h3>Att Val: {{botObj.healthValue}}</h3>
            <div>
                <button>SELECT</button>
                <button>RETIRE</button>
            </div>
        </div> -->
    </div>
</template>

<script>
import Bot from './Bot/Bot'

export default {
    props: ['botObj'],
    methods: {

    },
    components: {
        Bot
    }
}
</script>

<style scoped>
    
</style>