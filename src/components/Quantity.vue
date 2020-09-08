<template>
  <div class="quantity">
    <select name="quantity" class="quantity--select">
      <option value="1">Qty: 1</option>
      <option value="2">Qty: 2</option>
      <option value="3">Qty: 3</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "Quanitity",
};
</script>

<style lang="scss">
.quantity {
  width: 80%;
  transform: translateY(-10px);
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  &--select {
    width: 100%;
    padding: 20px 15px;
    font-family: "DM Sans", sans-serif;

    font-size: 20px;
    font-weight: 700;
    border: 2px solid rgba(119, 119, 119, 0.4);
    outline: none;
    overflow: hidden !important;
    background-color: #f2f3f5;
    border-radius: 7px;
    &:active,
    &:focus {
      outline: none;
    }
  }
  &--select.decorated option:hover {
    background: #32c574 !important ;
  }
}
</style>
