<template>
  <div id="app">
    <div id="todoList">
      <InputForm :add='add' />
      <List v-bind:listData="listData" :modify='modify' />
    </div>
  </div>
</template>

<script>
import List from './components/List'
import InputForm from './components/InputForm'

const a = [
            {
              name: 'test1', 
              no: 0, 
              modify: false,
              complete: false
            }
          ];

export default {
  name: 'App',
  components: {
    List,
    InputForm
  },
  data() {
    return {
      listData: a,
    }
  },
  methods: {
    add(val) {
        const list = this.listData;
        let n = list[list.length-1] ? list[list.length-1].no + 1 : 0;

        if(val) {
          this.listData.push({
              name: val,
              no: n,
              modify: false,
              complete: false
          });
        }
    },
    modify(n) {
      this.listData[n].modify = (this.listData[n].modify) ? false : true;
    },
  },
}
</script>

<style>
* { margin:0; padding:0; }
body { padding:10px; }
ul li { list-style:none; padding:5px 0; }
ul li input { margin-right:5px; }
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#todoList { width:500px; border:1px solid #999; margin:0 auto; padding:10px 0; }
#todoList ul li {}
#todoList ul li:nth-child(2n+1) { background:#eee; }
#todoList ul li a { font-size:12px; }
</style>
