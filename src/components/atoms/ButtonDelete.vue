<template>
    <button class="btn">
        <img src="/images/delete.svg" class="btn-photo" />
    </button>
</template>
<script>
export default {
    name: 'button-delete'
}
</script>

<style lang="sass" scoped>
$yellow: #FFDD00
$hover: #FFD400
.btn 
    border: none
    border-radius: 15%
    background: $yellow
    cursor: pointer
    padding: 10px
    margin: 2px
    transition: background 0.5s
    &-photo 
        width: 30px
.btn:hover
    background: $hover
</style>