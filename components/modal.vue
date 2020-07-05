<template>
  <portal to="modal">
    <div v-if="isVisible" class="modal-wrapper">
      <div class="modal">
        <section class="content">
          <h2 class="header">
            モーダルだよ
          </h2>
          <div class="body">
            hoge
          </div>
        </section>
        <button @click="close">
          close
        </button>
      </div>
    </div>
  </portal>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    isVisible: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    close (e: unknown) {
      this.$emit('close', e)
    }
  }
})
</script>

<style scoped>
.modal-wrapper {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;

  display: flex;
  align-items: center;
  justify-content: center;
}
.modal {
  width: 480px;
  height: 200px;

  background-color: #fff;
  border-radius: 2px;

  display: flex;
  align-items: center;
  flex-direction: column;

  padding: 16px;
}

.content {
  height: 100%;
  width: 100%;
}
</style>
