<template>
  <div>
      <ul>
          <li v-for="(a, index) in listData" :key="a.no" :data-num='a.no'>
              <input type="checkbox" :checked="false" />{{a.name}}
              <a href="#" @click='deleted(index)'>삭제</a>
          </li>
      </ul>
  </div>
</template>

<script>

export default {
  name: 'List',
  props: ['listData'],
  methods: {
    deleted(n) {
        this.listData.splice(n, 1);
    },
  }
}
</script>
