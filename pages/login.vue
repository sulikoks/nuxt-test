<template>
    <section>
        <nuxt-link class="nav-link" to="/"><h1>SULO</h1></nuxt-link>
        <form>
            <div class="form-group">
                <label for="login">Login</label>
                <input type="login" class="form-control" id="login" placeholder="Enter login">
            </div>
            <div class="form-group">
                <label for="password">Password</label>
                <input type="password" class="form-control" id="password" placeholder="Password">
            </div>
            <button type="submit" class="btn btn-primary">Login</button>
        </form>
    </section>
</template>

<script>
export default {
    layout: 'empty' //Задаем кастомный лайаут
}
</script>

<style scoped>
    h1 {
        text-align: center;
        margin: 0 auto;
    }
    form {
        margin-top: 3em;
        width: 500px;
    }
</style>