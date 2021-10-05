<template>
  <div>
      <p> {{title}} </p>
  </div>
</template>

<script>
export default {
    props: {
        title: String,
        id: Number,
        status: Boolean
    }
}
</script>

<style>

</style>