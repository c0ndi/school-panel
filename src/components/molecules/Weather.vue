<template>
    <div class="weather-box">
        <div class="weather-box-degree">
            <img
                src="/images/Sunny.png"
                class="weather-box-degree-photo"
                v-if="typeOfWeather === 'Clear'"
            />
            <img
                src="/images/Clouds.png"
                class="weather-box-degree-photo"
                v-if="typeOfWeather === 'Clouds'"
            />
            <img
                src="/images/Snowy.png"
                class="weather-box-degree-photo"
                v-if="typeOfWeather === 'Snow'"
            />
            <span class="weather-box-degree-temperature">{{ temperature }}&deg;C</span>
        </div>
        <div class="weather-box-type">
            <span class="weather-box-type-text">{{ typeOfWeather }}</span>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'weather',
    data() {
        return {
            temperature: null,
            typeOfWeather: null,
        }
    },
    mounted() {
        axios
            .get('https://api.openweathermap.org/data/2.5/weather?q=Czeladz&appid=9bcde8221acaaf7528ce8a9e68467c81')
            .then(response => {
                this.temperature = (response.data.main.temp - 272).toFixed(0)
                this.typeOfWeather = response.data.weather[0].main
            })
    }
}
</script>

<style lang="sass" scoped>
$gray: #5F5F5F
.weather-box
    margin-top: 10px
    border-radius: 15px
    width: 100%
    box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04), 0px 4px 16px rgba(51, 51, 51, 0.08)
    background: white
    color: $gray
    font-weight: 600
    &-degree
        height: 70%
        display: flex
        align-items: center
        justify-content: space-around
        padding: 5px
        &-photo
            height: 100%
        &-temperature
            font-size: 3.5rem
    &-type
        height: 30%
        display: flex
        align-items: center
        justify-content: center
        &-text
            font-size: 2rem
            font-weight: 700
</style>