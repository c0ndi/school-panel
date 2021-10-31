<template>
    <div class="todo-item">
        <div class="todo-item-text">
            <data-todo />
            <text-todo v-bind:textTodo="textTodo" />
        </div>
        <div class="todo-item-buttons">
            <button-complete @click="completeTodo(textTodo, itemIndex)" />
            <button-delete @click="removeTodo(itemIndex)" />
        </div>
    </div>
</template>

<script>
import ButtonDelete from "../atoms/ButtonDelete.vue"
import ButtonComplete from "../atoms/ButtonComplete.vue"
import TextTodo from "../atoms/TextTodo.vue"
import DataTodo from "../atoms/DataTodo.vue"

export default {
    name: 'todo-item',
    props: {
        textTodo: String,
        itemIndex: Number,
        removeTodo: {
            type: Function,
        },
        completeTodo: {
            type: Function,
        }
    },
    components: {
        'text-todo': TextTodo,
        'data-todo': DataTodo,
        'button-delete': ButtonDelete,
        'button-complete': ButtonComplete,
    },
}
</script>

<style lang="sass" scoped>
.todo-item 
    width: 100%
    height: 100%
    border-radius: 10px
    box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04), 0px 4px 16px rgba(51, 51, 51, 0.08)
    display: flex
    justify-content: space-between
    align-items: center
    &-text
        display: flex
        flex-direction: column
        margin: 10px
    &-buttons 
        display: flex
        margin: 10px
        height: 80%
</style>