
<script lang="ts">
  import { ref, defineComponent, getCurrentInstance } from 'vue'
  export default defineComponent({
    props: {
      msg: {
        type: String,
        default: ''
      }
    },
    setup() {
      const count = ref(0)
      const { proxy } = getCurrentInstance()!
      const sayHi = () => {
        proxy?.$message.success('halo')
        proxy?.$message.error({
          message: '1'
        })
      }
      return {
        count
      }
    }
  })
</script>
<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
