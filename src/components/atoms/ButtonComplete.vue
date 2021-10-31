<template>
    <button class="btn">
        <img src="images/complete.svg" class="btn-photo" />
    </button>
</template>
<script>
export default {
    name: 'button-complete',
}
</script>

<style lang="sass" scoped>
$orange: #FFAA00
$hover: #FF8717
.btn 
    border: none
    border-radius: 15%
    background: $orange
    cursor: pointer
    padding: 10px
    margin: 2px
    transition: background 0.5s
    &-photo 
        width: 30px
.btn:hover
    background: $hover
</style>