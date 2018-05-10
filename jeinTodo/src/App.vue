<template>
  <div id="app">
    <List
      v-bind:list="items"
      v-bind:removeItem="remove"
      v-bind:modifyItem="modify"
    />
    <Field v-bind:addItem="add" />
  </div>
</template>

<script>
import List from './components/List'
import Field from './components/Field'
let key = 0;
let data = (() => {
  let a = [];
  let l = 5;
  for (let i = 0; i < l; i++ ) {
    a.push({
      key: key++,
      title: 'title ' + key,
      complete: false
    })
  }
  return a;
})();

export default {
  name: 'App',
  components: {
    List,
    Field
  },
  data () {
    return {
      items: data
    }
  },
  methods: {
    add(data) {
      this.items.push({ title: data, complete: false, key: key++});
    },
    modify(index, title) {
      this.items.find(data => data.key === parseInt(index)).title = title;
    },
    remove(index) {
      let realIndex = this.items.indexOf(this.items.find(data => data.key === parseInt(index)));
      this.items.splice(realIndex, 1);
    }
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
