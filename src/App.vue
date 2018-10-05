<template>
  <div id="app">
      <v-app>
        <v-content>
          <v-container>
            <img src="./assets/logo.png">
            <h1><v-icon>library_music</v-icon> {{ msg }}</h1>
            <v-date-picker v-model="birthday" :landscape="landscape" :reactive="reactive"></v-date-picker>
            <br>
            Edad: {{ age }}
          </v-container>
        </v-content>
      </v-app>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Music!',
      birthday: null,
      landscape: true,
      reactive: false
    }
  },

  computed: {
    age () {
      let birthDate = new Date(this.nacimiento)
      let diffMs = Date.now() - birthDate.getTime()
      let ageDt = new Date(diffMs)

      return this.nacimiento
        ? Math.abs(ageDt.getUTCFullYear() - 1970)
        : 0
    }
  }
}
</script>

<style lang="scss">
@import './scss/main.scss'
</style>
