<template>
    <section>
        <h1>{{pageTitle}}</h1>
        <ul>
            <li v-for="user of users" :key="user.id"> <!--Как ключь для цикла v-for используем user.id -->
                <a href="#" @click.prevent="goTo(user)">
                    User {{user.name}} ({{user.email}})
                </a>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    asyncData({$axios,error}) { //вызывается на серверной части и после уже
        return $axios.$get('https://jsonplaceholder.typicode.com/users')
        .then(users => ({users}))
        .catch(err => {error(err)})
    },
    //new Promise(function(resolve, reject){
    //        setTimeout(() => {
    //            resolve({
    //                users: [
    //                    1,2,3,4,5,6,7,8
    //                ]
    //            });
    //        }, 500);
    //    })
    data: () => ({
        pageTitle: 'Users page'
    }),
    methods: {
        goTo(user) {
            this.$router.push('/users/' + user.id);
        }
    }
}
</script>