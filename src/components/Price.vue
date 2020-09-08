<template>
	<div class="price">
		<h4 class="price--product-name">
			{{ productInfo.name }}
		</h4>
		<h4 class="price--product-name">
			{{ productInfo.contain }}
		</h4>
		<div class="price--rating">
			<div
				class="price--rating-star"
				v-for="i in productInfo.rating + 1"
				v-bind:key="i"
			>
				<i class="fas fa-star"></i>
			</div>
			<div class="price--rating-star">
				<i class="fas fa-star-half-alt"></i>
			</div>
			<p class="price--rating-text">{{ productInfo.rating }} stars</p>
		</div>
    <div class="price--product">
      <h4 class="price--product-text">$ {{productInfo.price}}</h4>
    </div>
	</div>
</template>

<script>
export default {
	name: "Price",
	props: {
		productInfo: {
			type: Object,
			required: true,
		},
	},
};
</script>

<style lang="scss">
.price {
	text-align: center;
	&--product-name {
		font-size: 30px;
		line-height: 36px;
	}
	&--rating {
		display: flex;
		flex-direction: row;
    justify-content: center;
    padding-top: 10px;
    &-star{
      font-size: 30px;
      margin: 2px;
      color: #f2c94c;
    }
    &-text{
      font-size: 20px;
      margin: auto 0;
      margin-left: 10px;
    }
	}
  &--product{
    padding-top: 10px;
    &-text{
      font-size: 38px;
      font-style: normal;
      font-weight: 400;
    }
  }
}
</style>
