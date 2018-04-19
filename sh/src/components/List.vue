<template>
  <div>
      <ul>
          <li v-for="a in listData" :key="a.no"><input type="checkbox" :checked="false" />{{a.name}}</li>
      </ul>
  </div>
</template>

<script>
const a = [{name: 'test1', no: 0}, {name: 'test2', no: 1}];

export default {
  name: 'List',
  data() {
      return {
          listData: a
      }
  }
}
</script>
