<template>
    <span class="text-todo">{{ textTodo }}</span>
</template>

<script>
export default {
    props: ['textTodo'],
    data() {
        return {
            text: 'Make a dinner'
        }
    }

}
</script>

<style lang="sass" scoped>
$orange: #FFAA00
.text-todo 
    color: $orange
    font-size: 1.5rem
</style>