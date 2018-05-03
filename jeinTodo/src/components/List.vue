<template>
  <div class="list">
    <ul>
      <li v-for="item in data"><label><input type="checkbox" :checked="item.complete" v-bind:id="item.key" />{{item.title}}</label>
        <button v-on:click="editMode" v-bind:id="item.key">수정</button>
        <button v-on:click="modify" v-bind:id="item.key">수정완료</button>
        <button v-on:click="remove" v-bind:id="item.key">제거</button>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'List',
  props: ["data", "modifyItem", 'removeItem'],
  methods: {
    modify(data) {
      this.modifyItem(data.target.id)
    },
    remove(data) {
      this.removeItem(data.target.id)
    },
    editMode() {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
