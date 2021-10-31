<template>
    <div class="todo-box">
        <div class="todo-box-header">
            <div class="todo-box-header-left header-box">
                <span class="todo-box-header-left-text">
                    <span>Todo</span>
                    <span class="todo-box-header-left-text-lightText">list</span>
                </span>
            </div>
        </div>
        <div class="todo-box-input">
            <input
                type="text"
                v-model="todoText"
                class="todo-box-input-field"
                v-bind:placeholder="placeholderText"
            />
            <button @click="addTodo" class="todo-box-input-btn">Add</button>
        </div>
        <div v-for="(complete, index) in completed" v-bind:key="index">
            <p>{{ complete }}</p>
        </div>
        <div class="todo-box-output">
            <div class="todo-box-output-todos" v-for="(todos, index) in todo" v-bind:key="index">
                <todo-item
                    v-bind:textTodo="todo[index]"
                    :removeTodo="removeTodo.bind(index)"
                    :completeTodo="completeTodo.bind(todos, index)"
                    :itemIndex="index"
                />
            </div>
        </div>
    </div>
</template>
<script>
import ButtonCompleted from '../atoms/ButtonCompleted.vue'
import TodoItem from '../molecules/TodoItem.vue'

export default {
    name: 'todo-list',
    components: {
        'todo-item': TodoItem,
        'button-completed': ButtonCompleted,
    },
    data() {
        return {
            todoText: '',
            todo: [],
            placeholderText: "What's you gonna do?",
        }
    },
    methods: {
        addTodo() {
            if (this.todoText !== '') {
                this.placeholderText = "What's you gonna do?"
                this.todo.push(this.todoText)
                this.todoText = ''
            } else {
                this.placeholderText = 'You need to type something to add todo..'
            }
        },
        removeTodo(index) {
            this.todo = this.todo.filter((_, i) => index !== i)
        },
        completeTodo(todos, index) {
            console.log(123)
        },
    }
}
</script>

<style lang="sass" scoped>
$orange: #FFAA00
$hover: #FF8717
.todo-box 
    background-color: white
    display: flex
    flex-direction: column
    align-items: center
    width: 45%
    height: 90%
    border-radius: 15px
    margin: 10px
    box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04), 0px 4px 16px rgba(51, 51, 51, 0.08)
    &-header
        display: flex
        width: 100%
        align-items: center
        height: 10%
        justify-content: space-around
        &-left-text 
            color: $orange
            font-size: 3rem
            font-weight: 700
            &-lightText
                font-weight: 300
                font-size: 2rem
    &-input
        height: 20%
        width: 100%
        display: flex
        margin-top: 20px
        justify-content: space-around
        align-items: center
        &-field
            border: 0
            background: #fff
            width: 75%
            height: 40%
            border-radius: 10px
            box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04), 0px 4px 16px rgba(51, 51, 51, 0.08)
            padding: 10px
            font-size: 1rem
            outline: none 
        &-btn
            width: 15%
            height: 40%
            color: white
            background: $orange
            border: 0
            font-size: 1rem
            font-weight: 600
            cursor: pointer
            border-radius: 10px
            padding: 10px 10px
            transition: background 0.5s
        &-btn:hover
            background: $hover
        ::placeholder
            color: gray
    &-output
        width: 100%
        height: 70%
        display: flex
        flex-direction: column
        align-items: center
        &-todos
            width: 95%
            display: flex
            flex-direction: column
            align-items: center
</style>


