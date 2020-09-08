<template>
  <div class="button">
    <button class="button-cart">{{buttonText}}</button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    buttonText: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.button {
  width: 80%;
  margin-top: 20px;
  &-cart {
    width: 100%;
    background-color: #32c574;
    outline: none;
    border: none;
    padding: 20px 0;
    transition: all 0.3s;
    font-size: 24px;
    font-family: "DM Sans", sans-serif;
    color: #fff;
    border-radius: 8px;
    box-shadow: 0 5px 10px rgba(50, 197, 116, 0.59);
    &:active,
    &:focus {
      transform: translateY(5px);
    }
  }
}
</style>