<template>
    <div class="data-box">
        <span class="data-box-content">{{ data }}</span>
    </div>
</template>

<script>
export default {
    name: 'data-box',
    data() {
        return {
            data: new Date().toLocaleDateString()
        }
    }
}
</script>

<style lang="sass" scoped>
$gray: #5F5F5F
.data-box
    margin-top: 10px
    background: white
    border-radius: 15px
    width: 100%
    box-shadow: 0px 4px 4px rgba(51, 51, 51, 0.04), 0px 4px 16px rgba(51, 51, 51, 0.08)
    text-align: center
    &-content
        color: $gray
        font-weight: 700
        font-size: 2rem
        display: inline-block
        padding: 15px
</style>