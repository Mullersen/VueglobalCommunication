<template>
  <div>
      <h1>{{author}}</h1>
      <p>{{content}}</p>
  </div>
</template>

<script>
export default {
    name: "Tweet", 
    props: {
        author: String,
        content: String,
    }

}
</script>

<style>

</style>