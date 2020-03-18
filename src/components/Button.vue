<template>
  <button @click="notifyApp">Click me to toggle the view</button>
</template>

<script>
export default {
    name: "Button", 
    methods: {
        notifyApp(){
            this.$root.$emit("toggleView")
        }
    }
}
</script>

<style>

</style>