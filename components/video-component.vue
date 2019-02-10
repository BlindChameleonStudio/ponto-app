<template>
  <div class="video">
    <p>jméno</p>
    <input type="text" v-model="name">
    <p>jméno</p>
    <input type="text" v-model="email">
    <button type="button" name="button" @click='alert'>Odeslat</button>
    <h1>{{ test }}</h1>
  </div>

</template>
<script>
  export default {
    name: 'videoComponent',
    data () {
      return {
        name: null,
        email: null
      }
    },
    methods: {
      alert () {
        alert(this.name)
      }
    }
  }
</script>
<style>
h1 {
  color: red;
}
</style>
