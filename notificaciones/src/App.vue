<script setup>
import { ref } from 'vue'

let qty = ref(2)

function addValue(n) {
  qty.value += n
  console.log(qty)
}

function minusValue() {
  if (qty.value > 0) {
    qty.value--
  }
}
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="ballon" v-show="qty > 0">{{ qty }}</div>
    </div>

    <div class="button-wrapper">
      <div class="button" @click="minusValue">-</div>
      <div class="button" @click="addValue(5)">+</div>
    </div>

    <div v-if="qty > 0">Me escribieron 😁</div>
    <div v-else>Nadie me escribe 😭</div>
  </div>
</template>

<style scoped>
.button {
  background-color: #f2e8df;
  display: inline-block;
  padding: 4px 0;
  border-radius: 4px;
  width: 32px;
  margin: 0 8px;
}
.button:hover {
  cursor: pointer;
  background-color: #f2c6c2;
}

.button-wrapper {
  text-align: center;
  margin-top: 16px;
  margin-bottom: 16px;
}
.ballon {
  position: absolute;
  top: 0;
  right: 0;
  width: 32px;
  height: 32px;
  background-color: #f28585;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
.profile {
  background-image: url('https://elireview.com/wp-content/uploads/2016/12/reed-profile-square.jpg');
  background-size: cover;
  position: relative;
  background-color: orange;
  width: 160px;
  height: 160px;
  margin: 0 auto;
  border-radius: 100%;
}
.wrapper {
  overflow: hidden;
  padding-top: 18px;
  background-color: #86a69d;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
}
</style>
