<template>
  <div class="list">
    <ul>
      <li v-for="item in list"><label><input type="checkbox" :checked="item.complete" v-bind:id="item.key" />
        <span v-if="!editModes[item.key]">{{item.title}}</span>
        <input ref="title" v-if="editModes[item.key]" type="text" v-model="item.title" />
        </label>
        <button v-if="!editModes[item.key]" v-on:click="editMode" v-bind:id="item.key">수정</button>
        <button v-if="editModes[item.key]" v-on:click="modify" v-bind:id="item.key">수정완료</button>
        <button v-on:click="remove" v-bind:id="item.key">제거</button>
      </li>
    </ul>
  </div>
</template>

<script>

export default {
  name: 'List',
  props: ["list", "modifyItem", 'removeItem'],
  data: function () {
    let uiData = {};
    this.list.forEach(item => uiData[item.key] = uiData[item.key] || false)
    return {
      editModes: uiData
    }
  },
  methods: {
    modify(data) {
      this.modifyItem(data.target.id, this.$refs.title[0].value);
      this.editModes[data.target.id] = false;
    },
    remove(data) {
      this.removeItem(data.target.id)
    },
    editMode(data) {
      this.editModes[data.target.id] = true;
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
