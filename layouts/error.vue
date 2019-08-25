<template>
    <section>
        <h1>Error 404</h1>
        <nuxt-link :to="'/'">Home page</nuxt-link>
    </section>
</template>

<style scoped>
    h1 {
        color : red;
    }
    section {
        display: flex;
        align-items: center;
        flex-direction: column;
    }
</style>