<template>
  <div class="product" @click="pclick">
    <slot></slot>
    <!-- <div class="item">
      <div class="title">Tiitle1</div>
      <img src="../assets/logo.png" alt="" />
      <div class="price">1001</div>
    </div>
    <div class="item">
      <div class="title">Tiitle2</div>
      <img src="../assets/logo.png" alt="" />
      <div class="price">1002</div>
    </div>
    <div class="item">
      <div class="title">Tiitle3</div>
      <img src="../assets/logo.png" alt="" />
      <div class="price">1003</div>
    </div>
    <div class="item">
      <div class="title">Tiitle4</div>
      <img src="../assets/logo.png" alt="" />
      <div class="price">1004</div>
    </div> -->
  </div>
</template>
<script>
export default {
  methods: {
    pclick() {
      this.$emit("och");
    },
  },
};
</script>
<style>
.product {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 30px;
  padding: 50px;
}
.item {
  box-shadow: 0px 0px 10px grey;
  padding: 25px 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 15px;
}
.title {
  font-size: 24px;
  text-transform: uppercase;
  font-weight: bold;
}
.price {
  color: red;
  font-size: 18px;
  font-style: italic;
}
</style>
