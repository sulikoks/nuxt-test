<template>
    <div>
        <h1>{{title}} Вам всем {{use()}}</h1>
        <hr>
        <h2>Her name is {{user.name}}</h2>
        <b>{{user.email}}</b>
    </div>
</template>

<script>
export default {
    //validate({params}) {         //Обработка норм потестить
    //    console.log(params.id);
    //},
    ////////////////////////////////////////////////////////////////////////////////////////////////////////////////
    ///////////////////////////////////////////Решение №1 Подключение и забор параметров
    async asyncData({$axios, params, error}) {
        try {
            const user = await $axios.$get(`https://jsonplaceholder.typicode.com/users/${params.id}`);
            return {user}; //Возвращает User
        } catch (e) { //Обработка ошибки если есть
            error(e); //Вывести ошибку если есть
        }
    },
    data: () => ({
        title: 'Привет посанам хуй ворам',
        use: () => {
            return 5;
        }
    })
    ////////////////////////////////////////////////////////////////////////////////////////////////////////////////
    ///////////////////////////////////////////Решение №2 Подключение и забор параметров
    //asyncData({params, error, $axios}) {
    //    return $axios.$get(`https://jsonplaceholder.typicode.com/users/${params.id}`)
    //    .then(user => ({user})) //Функция принимает User от $axios.$get и возвращает {User}
    //    .catch(e => {error(e)}) //Обработка ошибки если есть
    //},      
    ////////////////////////////////////////////////////////////////////////////////////////////////////////////////
        //return new Promise((resolve, reject)=> { // Если обещание исполняется то
        //    setTimeout(() => { // Выполнение функции через 500 мсек
        //        //resolve({ //Когда пользователь найден(обещание сдержал)
        //        //    user: {
        //        //        name: `Test user ${params.id}`
        //        //    }
        //        //})
        //        reject( //Когда пользователь не найден
        //            error(new Error('User not found'))
        //        )
        //    }, 500)
        //})
    //}
}
</script>