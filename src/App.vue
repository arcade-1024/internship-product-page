<template>
	<div id="app">
		<ShopDetails />
	</div>
</template>

<script>
import ShopDetails from "./pages/ShopDetails";
export default {
	name: "App",
	components: {
		ShopDetails,
	},
};
</script>

<style lang="scss">
*,
*::after,
*::before {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
#app {
	font-family: "DM Sans", sans-serif;
}
</style>
