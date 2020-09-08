<template>
  <div class="option">
    <div v-for="item in comboOptions" v-bind:key="item.id">
      <label
        v-bind:class="{active:item.id === 1}"
        class="option--label"
        v-on:click="highlightOption"
        v-bind:for="item.id"
      >
        <input
          type="radio"
          class="option--label-radio"
          v-bind:id="item.id"
          v-bind:checked="item.id === 1"
          name="radio-btn"
        />
        <div class="option--label-radio-btn"></div>
        <div class="option--label-card">
          <h4 class="option--label-card-text">{{ item.qty }} {{ item.type }} - {{ item.price }}</h4>
          <p v-show="item.showSave" class="option--label-card-muted">
            <span class="option--label-card-muted-span" v-show="item.showOrgPrice">
              List price:
              <span class="option--label-card-muted-span-strike">USD {{ item.originalPrice }}</span>
            </span>
            save {{ item.save }}
          </p>
        </div>
      </label>
    </div>
  </div>
</template>

<script>
export default {
  name: "Options",
  props: {
    comboOptions: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {};
  },
  methods: {
    highlightOption: function (event) {
      const current = document.querySelector(".active");
      current.classList.remove("active");
      event.target.parentElement.classList.add("active");
    },
  },
};
</script>

<style lang="scss" scoped>
.option {
  margin: 20px 0 0 0;
  width: 80%;

  &--label {
    display: flex;
    flex-direction: row;
    border-radius: 7px;
    padding: 20px 15px;
    margin-bottom: 30px;
    background-color: rgba(240, 240, 240, 0.7);
    box-shadow: 0 4px 9px rgba(0, 0, 0, 0.4);
    transition: all 0.3s;
    cursor: pointer;

    &:hover {
      border: 2px solid rgb(0, 132, 255);
    }
    &-radio {
      display: none;
      &-btn {
        height: 20px;
        width: 20px;
        border-radius: 21px;
        border: 3px solid #32c574;
        margin: auto 0;
        margin-right: 10px;
        position: relative;
        &::after {
          content: "";
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%);
          height: 10px;
          width: 10px;
          background-color: #32c574;
          opacity: 0;
          border-radius: 11px;
          z-index: 100;
        }
      }
    }
    &-radio:checked + &-radio-btn::after {
      opacity: 1;
    }
    &-card {
      width: 100%;
      &-text {
        font-size: 20px;
      }
      &-muted {
        margin-top: 3px;
        text-align: right;
        position: relative;
        color: #32c574;
        font-weight: 700;
        &-span {
          position: absolute;
          left: 0;
          color: rgba(119, 119, 119, 0.6);
          font-weight: 400;
          &-strike {
            text-decoration: line-through;
          }
        }
      }
    }
  }
}
.active {
  border: 3px solid #32c574;
  box-shadow: 0px 4px 9px #32c5748c;
}
</style>
