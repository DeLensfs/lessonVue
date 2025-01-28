<template>
  <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>

  <button type="button" @click="userData('Some title')">Отправить</button>
</template>


<script>
export default {
  data() {
    return {
      info: 'Title!',
      someInfo: 'Anons of message'
    }
  },
  methods: {
    userData(word) {
      this.info=word;
      // this.info = 'Some Title'
      this.someInfo = 'Some Paragraph'

    }
  }
}
</script>












<style scoped>
h3 {
  font-weight: lighter;
}

p {
  color: rgb(160, 28, 28);
}
</style>
