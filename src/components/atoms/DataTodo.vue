<template>
    <span class="data-todo">{{ time }} &nbsp; {{ date }}</span>
</template>

<script>
export default {
    name: 'data-todo',
    data() {
        return {
            time: new Date().toLocaleTimeString(navigator.language, {
                hour: '2-digit',
                minute: '2-digit'
            }),
            date: new Date().toLocaleDateString(),
        }
    },
    // computed: {
    //     showDate() {
    //         return this.time + "" + this.date
    //     }
    // }
}
</script>

<style lang="sass" scoped>
$gray: #DBDBDB
.data-todo 
    color: $gray
    
</style>