<template>
  <button :id="id">{{title}}</button>
</template>

<script>
export default {
    props:{
        id: String,
        title: String
    }
}
</script>

<style>

</style>