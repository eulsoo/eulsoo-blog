<template>
  <div>{{ items }}</div>
</template>

<script>

export default {
  data () {
    return {
      items: []
    }
  },
  async mounted () {
    const sn = await this.$fireStore.collection('test').get()
    sn.docs.forEach((v) => {
      console.log(v.data())
      this.items.push(v.data())
    })
  }
}
</script>
