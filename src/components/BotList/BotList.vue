<template>
    <div>
        <bot
        :botObj='botObj' 
        :selectBot='selectBot'
        :retire='retire'/>
    </div>
</template>

<script>
import Bot from './Bot/Bot'

export default {
    props: ['botObj', 'selectBot','retire'],
    methods: {

    },
    components: {
        Bot
    }
}
</script>

<style scoped>
    
</style>