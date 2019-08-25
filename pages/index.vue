<template>
  <section> 
    <h1>Hello world, this is Home Page {{a}}!</h1>
  </section>
</template>

<script>
  export default{
    data: () => ({
      a: 123,
      n: 143,
    }),
    //asyncData: () => ({
    //    b: 23
    //})
    
  }
</script>

<style>
</style>
