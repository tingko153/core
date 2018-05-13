<template>
  <div>
      <ul>
          <Item v-for="a in listData" :key="a.no" :data-num='a.no' :item='a' v-on:deleteItem='deleted' />
          <!-- <li v-for="(a, index) in listData" :key="a.no" :data-num='a.no'>
            <input type="checkbox" v-model="a.complete" :value='a.no' />

            <input v-if="a.modify" type="text" v-model='a.name' @keyup.enter="modify(index)" />
            <span v-else>{{a.name}}</span>

            <a href="#" @click='modify(index)'>수정</a>
            <a href="#" @click='deleted(index)'>삭제</a>
          </li> -->
      </ul>
  </div>
</template>

<script>
import Item from './Item';

export default {
  name: 'List',
  props: ['listData', 'modify'],
  components: {
      Item
  },
  data() {
      return {

      }
  },
  methods: {
    deleted(n) {
        this.listData.splice(n, 1);
    },
  },
}
</script>
