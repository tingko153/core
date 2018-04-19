<template>
  <div class="list">
    <ul>
      <li v-for="item in items"><label><input type="checkbox" :checked="item.complete" id="`${item.title}`" />{{item.title}}</label></li>
    </ul>
  </div>
</template>

<script>
const items = [{title: 'aaaaaaaaaa', complete: false}, {title: 'bbbbbbb', complete: false}, {title: 'abcs', complete: true}];
export default {
  name: 'List',
  data () {
    return {
      items: items
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
