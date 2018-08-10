<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Header v-bind:title="title" />
    <ul>
      <li v-for="(item, index) in movies">{{ index + 1 }} {{ item }}</li>
      <li v-for="actor in actors"> {{ actor.name }}</li>

      <!-- LOOP THROUGH AN OBJECT -->
      <li v-for="(value, key) in profile"> {{key}}: {{ value }} </li>

      <!-- LOOPING OVER A COMPONENT 
      <Header 
        :key="actor.id"
        v-for="actor in actors"
        :title="actor.name"
      /--> 
    </ul>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header.vue'

export default {
  name: 'app',
  data() {
    return {
      message: 'test',
      title: 'Vue movie DB',
      movies: [
        'Terminator',
        'Gremlins',
        'Ghostbusters'
      ],
      actors: [
        { id: 1, name: 'Bill Murray'},
        { id: 2, name: 'Samuel L Jackson'}
      ],
      profile: {
        name: 'James Cameron',
        age: 'I dunno 70?',
        job: 'Director'
      }
    }
  },
  components: {
    HelloWorld,
    Header
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
