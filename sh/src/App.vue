<template>
  <div id="app">
    <InputForm :add='add' />
    <List v-bind:listData="listData" />
  </div>
</template>

<script>
import List from './components/List'
import InputForm from './components/InputForm'

const a = [{name: 'test1', no: 0}, {name: 'test2', no: 1}];

export default {
  name: 'App',
  data() {
    return {
      listData: a
    }
  },
  methods: {
    add(val) {
        this.listData.push({
            name: val,
            no: this.listData.length
        })
    },
    removeItem() {
      
    }
  },
  components: {
    List,
    InputForm
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
