<template>
  <h1>{{ title }}</h1>
  <p>welcome...</p>
  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
  <p>second section</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" :theme="theme" @close="toggleModal" />
  </div>
  <button @click="toggleModal">show modal</button>
</template>

<script>
import Modal from './components/Modal'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first Vue App ;-)',
      header: 'Test header for passing props',
      text: 'Here for testing text',
      theme: 'sale',
      showModal: false,
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
