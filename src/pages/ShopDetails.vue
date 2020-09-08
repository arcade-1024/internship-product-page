<template>
  <div class="shop-details">
    <Slider />
    <Price v-bind:productInfo="productInfo" />
    <Options v-bind:comboOptions="comboOptions" />
    <Quanitity />
    <Button v-bind:buttonText="buttonText" />
    <p class="savings-text">Buy now and save $ 10</p>
    <Description v-bind:DescriptionText="DescriptionText" />
  </div>
</template>

<script>
import Slider from "../components/Slider";
import Price from "../components/Price";
import Options from "../components/Options";
import Quanitity from "../components/Quantity";
import Button from "../components/Button";
import Description from "../components/Description";
export default {
  name: "ShopDetails",
  components: {
    Slider,
    Price,
    Options,
    Quanitity,
    Button,
    Description,
  },
  data() {
    return {
      productInfo: {
        id: 1,
        name: "Sunshine Bliss Daily",
        contain: "Vitamin D",
        rating: "4.8",
        price: "13.99",
      },
      comboOptions: [
        {
          id: 1,
          type: "gummies",
          qty: "30",
          originalPrice: "",
          price: "$ 10",
          showOrgPrice: false,
          save: "",
          showSave: false,
          selected: false,
        },
        {
          id: 2,
          type: "gummies",
          qty: "90",
          originalPrice: "30",
          price: "$ 20",
          showOrgPrice: true,
          save: "10%",
          showSave: true,
          selected: false,
        },
        {
          id: 3,
          type: "Monthly Subscription",
          qty: "",
          originalPrice: "",
          price: "",
          showOrgPrice: false,
          save: "20%",
          showSave: true,
          selected: false,
        },
      ],
      buttonText: "Add to Cart",
      DescriptionText: {
        Details:
          "An amino acid found in tea, L-theanine is similar to glutamic acid, an excitatory neurotransmitter found in the central nervous system. A precursor to acetylcholine,Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        HowTo:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        Ingredients:
          "commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.shop-details {
  display: flex;
  flex-direction: column;
  // justify-content: center;
  align-items: center;
  margin-top: 20px;
  // width: 60%;
}
.savings-text {
  color: #32c574;
  font-weight: 700;
  letter-spacing: 0.5px;
  font-size: 18px;
  margin-top: 15px;
}
</style>
