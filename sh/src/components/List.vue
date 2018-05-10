<template>
  <div>
      <ul>
          <li v-for="(a, index) in listData" :key="a.no" :data-num='a.no'>
              <input type="checkbox" :checked="false" v-model="a.complete" />
                <span v-if="a.modify===false">{{a.name}}</span>
                <input v-else type="text" v-model='a.name' @keyup.enter="modify(index)" />
              <a href="#" @click='modify(index)'>수정</a>
              <a href="#" @click='deleted(index)'>삭제</a>
          </li>
      </ul>
  </div>
</template>

<script>

export default {
  name: 'List',
  props: ['listData', 'modify'],
  methods: {
    deleted(n) {
        this.listData.splice(n, 1);
    },
  }
}
</script>
