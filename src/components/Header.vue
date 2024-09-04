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
        <RouterLink to="/InsidePage">InsidePage</RouterLink>
        <RouterLink to="/ConfirmationPage">ConfirmationPage</RouterLink>
        <RouterLink to="/StatisticPage">StatisticPage</RouterLink>
        <RouterLink to="/BackEnd">BackEnd</RouterLink>
        <RouterLink to="/BackEndInsidePage">BackEndInsidePage</RouterLink>
        <RouterLink to="/BackEndInsidePage2">BackEndInsidePage2</RouterLink>
        <RouterLink to="/BackEndInsidePage3">BackEndInsidePage3</RouterLink>
        <RouterLink to="/FillinPage">FillinPage</RouterLink>
    </div>
</template>

<style scoped lang="scss">
.headerArea {
    width: 100%;
    height: 100%;
}
</style>