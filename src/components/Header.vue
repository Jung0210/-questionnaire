<script>
import { RouterLink } from 'vue-router'
export default {
    components: {
        RouterLink
    }
}
</script>

<template>
    <div class="headerArea">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/VtextAndVmodel">VtextAndVmodel</RouterLink>
    </div>
</template>

<style scoped lang="scss">
.headerArea {
    width: 100%;
    height: 100%;
}
</style>