<template>
    <div class="aside-box">
        <day-box />
        <data-box />
        <weather-box />
    </div>
</template>
<script>
import Day from "../molecules/Day.vue";
import Data from "../molecules/Data.vue";
import Weather from "../molecules/Weather.vue";

export default {
    name: 'aside-box',
    components: {
        'day-box': Day,
        'data-box': Data,
        'weather-box': Weather,
    }
}
</script>

<style lang="sass" scoped>
$orange: #FF9500
.aside-box 
    width: 35%
    height: 100%
    background-color: $orange
    display: flex
    flex-direction: column
    align-items: center
    padding: 10px 
</style>
