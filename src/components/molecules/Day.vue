<template>
    <div class="data-box">
        <span class="data-box-content">{{ getDay(new Date(), 'en-EN') }}</span>
    </div>
</template>

<script>
export default {
    name: 'day-box',
    data() {
        return {
            data: ''
        }
    },
    methods: {
        getDay(dataStr, locale) {
            const dataTerazEs = new Date(dataStr);
            return dataTerazEs.toLocaleDateString(locale, { weekday: 'long' });
        }
    }
}
</script>

<style lang="sass" scoped>
$gray: #5F5F5F
.data-box
    width: 100%
    background: white
    border-radius: 15px
    box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04), 0px 4px 16px rgba(51, 51, 51, 0.08)
    text-align: center
    &-content
        color: $gray
        font-weight: 700
        font-size: 2rem
        display: inline-block
        padding: 25px
</style>