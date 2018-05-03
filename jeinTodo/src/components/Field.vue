<template>
  <div class="add">
    <input type="text" ref="addText" /> <button v-on:click="add">추가</button>
  </div>
</template>

<script>
  export default {
    name: 'Field',
    props: ['addItem'],
    methods: {
      add() {
        this.addItem(this.$refs.addText.value);
        this.$refs.addText.value = '';
      }
    }
  }
</script>

