<template>
  <main class="main">
    <article class="main-article">
      <div class="main-article-left">
        <clock-box />
        <links-box />
      </div>
      <div class="main-article-right">
        <todo-list-box />
        <aside-box />
      </div>
    </article>
  </main>
</template>
<script>
import Clock from "./components/organism/Clock.vue"
import Links from "./components/organism/Links.vue"
import Aside from "./components/organism/Aside.vue"
import TodoList from "./components/organism/TodoList.vue"

export default {
  components: {
    'aside-box': Aside,
    'clock-box': Clock,
    'links-box': Links,
    'todo-list-box': TodoList
  }
}
</script>

<style lang="sass">
$primay: #FF9500
$secondary: #FFAA00
$darkGray: #5F5F5F
*
  box-sizing: border-box
  font-family: 'Montserrat' 
body 
  margin: 0
  padding: 0
  // 
    // 
      // 
.main 
  width: 100%
  height: 100vh
  display: flex
  flex-direction: row
  border: 1px solid blue
  &-article
    display: flex
    width: 100%
    &-left
      width: 50%
      height: 100%
      display: flex
      flex-direction: column
      justify-content: space-between
      padding: 20px
      border: 1px solid red
    &-right
      display: flex
      justify-content: flex-end
      align-items: center
      width: 50%
      height: 100%
      border: 1px solid red

@media (min-width: 1025px) and (max-width: 1280px)
    .main
      display: flex
      flex-direction: column
      &-article
        display: flex
        flex-direction: column
        &-left
          width: 100%
        &-right
          width: 100%        
@media (min-width: 768px) and (max-width: 1024px)
    .main
      display: flex
      flex-direction: column
      &-article
        display: flex
        flex-direction: column
        &-left
          width: 100%
        &-right
          width: 100%
@media (min-width: 768px) and (max-width: 1024px) and (orientation: landscape)
    .main
      display: flex
      flex-direction: column
      &-article
        display: flex
        flex-direction: column
        &-left
          width: 100%
        &-right
          width: 100%
@media (min-width: 481px) and (max-width: 767px)
    .main
      display: flex
      flex-direction: column
      &-article
        display: flex
        flex-direction: column
        &-left
          width: 100%
        &-right
          width: 100%
@media (min-width: 320px) and (max-width: 480px)
    .main
      display: flex
      flex-direction: column
      &-article
        display: flex
        flex-direction: column
        &-left
          width: 100%
        &-right
          width: 100%
</style>
