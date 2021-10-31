<template>
    <button class="btn">Completed</button>
</template>

<script>

export default {
    name: 'button-completed'
}
</script>


<style lang="sass" scoped>
$orange: #FFAA00
.btn 
    color: white
    background: $orange
    border: 0
    font-size: 0.75rem
    font-weight: 600
    cursor: pointer
    border-radius: 10px
    height: 40px
</style>