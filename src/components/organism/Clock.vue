<template>
    <div class="clock">
        <span class="clock-time">{{ refreshTime() }}</span>
    </div>
</template>
<script>
export default {
    name: 'clock',
    data() {
        return {
            time: new Date().toLocaleTimeString()
        }
    },
    methods: {
        refreshTime() {
            const timer = setInterval(() => {
                this.time = new Date().toLocaleTimeString()
                clearInterval(timer)
            }, 1000)
            return this.time
        }
    }
}
</script>

<style lang="sass" scoped>
$gray: #DBDBDB
.clock 
    text-align: center
    margin: 10px
    &-time
        color: $gray
        font-size: 15rem
        font-weight: 700
</style>
