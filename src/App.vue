<template>
  <div id="app">
    <app-second></app-second>
      <h1>{{ title }}</h1>
        <button @click="title = 'Changed'">Change Title</button>
      <app-greeting :greeting="title" v-on:newChange="title = $event">
        <h1 slot="first">Hello This is a slot </h1>
        
        <h2 slot="second">Sub title</h2>
        <h3>default slot</h3>
      </app-greeting>

  </div>
</template>

<script>
import Greetings from './components/Greetings';
import Second from './components/Second';
export default {
  data(){
    return {
        title: 'Parent Component'
    }
  },
  components: {
    'app-greeting': Greetings,
    'app-second': Second
  }
}
</script>

<style scoped>
#app {
  background-color: aquamarine;
  width: 500px;
  height: 500px;
  border: 2px solid black;
}

button {
  margin-bottom: 20px;
}
</style>
