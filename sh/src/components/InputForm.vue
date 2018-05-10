<template>
    <div>
        <input type="text" v-model='value' @keyup.enter='add2'/><button @click='add2' >add</button>
    </div>
</template>

<script>
export default {
    name: 'InputForm',
    props: ['add'],
    data() {
        return {
            value: ''
        }
    },
    methods: {
        add2() {
            this.add(this.value);
            this.value = '';
        }
    }
}
</script>

