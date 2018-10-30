<template>
    <div>
        <bot 
        :botObj='botObj' 
        :selectBot='selectBot'/>
    </div>
</template>

<script>
import Bot from './Bot/Bot'

export default {
    props: ['botObj', 'selectBot'],
    methods: {

    },
    components: {
        Bot
    }
}
</script>

<style scoped>
    
</style>