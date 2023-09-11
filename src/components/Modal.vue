<template lang="">
  <div class="bgDrop" @click.self="closeModal">
    <div class="modal">
      <span @click.self="closeModal">X</span>

      <h3>{{ textModal }}</h3>

      <hr />

      <slot></slot>

      <hr />

      <slot name="links"></slot>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: ["textModal"],
  methods: {
    closeModal(this: any): void {
      this.$emit("close-modal");
    },
  },
};
</script>

<style scoped lang="scss">
.bgDrop {
  position: fixed;
  top: 0;
  left: 0;
  background-color: rgb(0, 0, 0, 0.5);
  height: 100dvh;
  width: 100%;
  .modal {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 500px;
    padding: 20px;
    background-color: white;
    border-radius: 10px;
    font: bold 24px arial;
    color: #4b4b4b;
    box-shadow: 0px 2px 16px rgb(0, 0, 0, 0.5);
    span {
      position: absolute;
      right: 12px;
      top: 12px;
      background-color: red;
      border-radius: 50%;
      color: white;
      width: 24px;
      height: 24px;
      font: 100 22px arial;
      cursor: pointer;
    }
    h3{
      color: #000;
    }
    hr {
      margin: 16px 0;
    }
    p {
      font: bold 16px arial;
      text-align: center;
      color: #2b2b2b;
      padding: 8px 16px;
      margin-top: 32px;
      border: none;
      border-radius: 4px;
    }
  }
}
</style>
