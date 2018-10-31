<template>
  <div class="container">
    <div class="alert-confirm">
      <div>{{ additionalMessage }}</div>
      <div>Вы уверены?</div>
      <div>
        <button @click="agreeAction">Да</button>
        <button @click="disagreeAction">Нет</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AlertConfirm',
  props: {
    additionalMessage: String
  },
  methods: {
    agreeAction () {
      this.$emit('isAgree')
    },
    disagreeAction () {
      this.$emit('isDisagree')
    }
  }

}
</script>

<style lang="less" scoped>
.container {
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  opacity: 1;
  z-index: 800;
  transition: opacity 0.3s ease-out;
  & .alert-confirm {
    width: 500px;
    background-color: white;
  }
}
</style>
