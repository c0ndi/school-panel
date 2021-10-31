<template>
    <ul class="links">
        <li class="links-li">
            <a href="#" class="links-li-a">Github</a>
        </li>
        <li class="links-li">
            <a href="#" class="links-li-a">C0ndi</a>
        </li>
        <li class="links-li">
            <a href="#" class="links-li-a">Youtube</a>
        </li>
        <li class="links-li">
            <a href="#" class="links-li-a">Metahero - cmc</a>
        </li>
        <li class="links-li">
            <a href="#" class="links-li-a">Metahero.io</a>
        </li>
        <li class="links-li">
            <a href="#" class="links-li-a">Facebook</a>
        </li>
        <li class="links-li">
            <a href="#" class="links-li-a">Figma</a>
        </li>
    </ul>
</template>
<script>
export default {
    name: "links"
}
</script>

<style lang="sass">
$gray: #dbdbdd
.links 
    padding: 0
    margin: 0
    list-style-type: none
    &-li 
        padding: 5px
        &-a
            font-weight: bold
            font-size: 1.5rem
            color: #dbdbdd
            text-decoration: none
            &:visited, &:hover, &:active
                color: $gray
</style>
