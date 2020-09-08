<template>
  <div class="description">
    <div class="description--header">
      <ul class="description--header-list">
        <li
          v-bind:class="{ active: isDetailActive }"
          class="description--header-list-item"
          v-on:click="togglDetails"
        >Details</li>
        <li
          v-bind:class="{ active: isProcessActive}"
          class="description--header-list-item"
          v-on:click="toggleProcess"
        >How to take it</li>
        <li
          v-bind:class="{active: isIngredientActive}"
          class="description--header-list-item"
          v-on:click="toggleIngredients"
        >Ingredients</li>
      </ul>
    </div>
    <div v-show="isDetailActive" class="description--main">
      <p v-show="!readMore">{{DescriptionText.Details.substring(0,300)}}</p>
      <p v-show="readMore" class="u-padding-bottom">{{DescriptionText.Details}}</p>
      <h5 v-on:click="toggleRead" class="description--main-readMore">Read more</h5>
    </div>
    <div v-show="isProcessActive" class="description--main">
      <p v-show="!readMore">{{DescriptionText.HowTo.substring(0,300)}}</p>
      <p v-show="readMore" class="u-padding-bottom">{{DescriptionText.HowTo}}</p>
      <h5 v-on:click="toggleRead" class="description--main-readMore">Read more</h5>
    </div>
    <div v-show="isIngredientActive" class="description--main">
      <p v-show="!readMore">{{DescriptionText.Ingredients.substring(0,300)}}</p>
      <p v-show="readMore" class="u-padding-bottom">{{DescriptionText.Ingredients}}</p>
      <h5 v-on:click="toggleRead" class="description--main-readMore">Read more</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "Description",
  props: {
    DescriptionText: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      isDetailActive: true,
      isProcessActive: false,
      isIngredientActive: false,
      readMore: false,
    };
  },
  methods: {
    togglDetails: function () {
      this.isDetailActive = true;
      this.isProcessActive = false;
      this.isIngredientActive = false;
    },
    toggleProcess: function () {
      this.isDetailActive = false;
      this.isProcessActive = true;
      this.isIngredientActive = false;
    },
    toggleIngredients: function () {
      this.isDetailActive = false;
      this.isProcessActive = false;
      this.isIngredientActive = true;
    },
    toggleRead: function () {
      this.readMore = !this.readMore;
    },
  },
};
</script>

<style lang="scss">
.description {
  margin-top: 20px;
  width: 80%;

  &--header {
    width: 100%;
    &-list {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      list-style: none;
      &-item {
        font-size: 18px;
        padding-bottom: 3px;
        font-weight: 500;
      }
    }
  }
  &--main {
    margin-top: 8px;
    line-height: 28px;
    font-size: 16px;
    &-readMore {
      padding-top: 15px;
      color: #2f80ed;
      transform: translateY(-18px);
      text-align: right;
      font-size: 20px;
      line-height: 21px;
      background: linear-gradient(180deg, rgba(255, 255, 255, 0) 0%, #fff 25%);
      transition: all 0.3s;
      cursor: pointer;
      &:active,
      &:focus {
        transform: translateY(8px);
      }
    }
  }
}
.active {
  border-bottom: 3px solid #f8d702;
  font-weight: 700;
}
.u-padding-bottom {
  padding-bottom: 20px;
}
</style>