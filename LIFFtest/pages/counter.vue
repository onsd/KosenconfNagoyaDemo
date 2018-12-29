<template>
  <section class="container">
    <div>
      <h1>usersのindexページです。</h1>
      <p>count={{count}}</p>
      <button @click="addCount" class="button is-primary is-outlined">カウントアップ</button>
    </div>
  </section>
</template>

<script>
export default {
  computed: {
    count () { return this.$store.state.counter.count }
  },
  methods: {
    addCount (e) {
      this.$store.commit('counter/add')
    }
  }
}
</script>