<template>
  <div class="slider">
    <div class="slider--main">
      <img v-bind:src="mainImg" alt />
    </div>
    <div class="slider--bar">
      <div class="slider--bar-dots dotActive" v-on:click="changeActive"></div>
      <div class="slider--bar-dots" v-on:click="changeActive"></div>
      <div class="slider--bar-dots" v-on:click="changeActive"></div>
      <div class="slider--bar-dots" v-on:click="changeActive"></div>
    </div>
    <div class="slider--small">
      <div class="slider--small-conatiner containerActive" v-on:click="changeImg">
        <img v-bind:src="images[1]" alt="productImg" />
      </div>
      <div class="slider--small-conatiner" v-on:click="changeImg">
        <img v-bind:src="images[2]" alt="productImg" />
      </div>
      <div class="slider--small-conatiner" v-on:click="changeImg">
        <img v-bind:src="images[1]" alt="productImg" />
      </div>
      <div class="slider--small-conatiner" v-on:click="changeImg">
        <img v-bind:src="images[1]" alt="productImg" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Slider",
  data() {
    return {
      mainImg: "https://arcade-1024.github.io/imageCodePen/Group316.png",
      images: [
        "https://arcade-1024.github.io/imageCodePen/Group316.png",
        "https://arcade-1024.github.io/imageCodePen/img1.png",
        "https://arcade-1024.github.io/imageCodePen/img2.png",
      ],
      isActive: true,
    };
  },
  methods: {
    changeActive: function (event) {
      const current = document.querySelector(".dotActive");
      current.classList.remove("dotActive");
      event.target.classList.add("dotActive");
      console.log(event.target);
    },
    changeImg: function (event) {
      const current = document.querySelector(".containerActive");
      current.classList.remove("containerActive");
      event.target.classList.add("containerActive");
      this.mainImg = event.target.src;
    },
  },
};
</script>

<style lang='scss' scoped>
.slider {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  margin-bottom: 20px;
  &--main {
    height: 230px;
    width: 80%;
    background: linear-gradient(to right bottom, #e8e7ed71, #e8e7ed);
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
  }
  &--bar {
    display: flex;
    width: 30%;
    margin: 20px 0;
    justify-content: space-between;
    &-dots {
      height: 10px;
      width: 10px;
      border-radius: 21px;
      background-color: #777;
      transition: all 0.5s;
    }
  }
  &--small {
    display: flex;
    justify-content: space-around;
    width: 90%;
    &-container {
      height: 100%;
      width: 100%;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.466);
      border-radius: 10px;
    }
  }
}
.containerActive {
  border: 3px solid #f8d702;
  transition: all 0.5s;
  border-radius: 8px;
  box-shadow: 0 5px 6px #f8d70267;
}
.dotActive {
  width: 40px;
  background-color: #f8d702;
}
</style>