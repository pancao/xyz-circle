<template>
  <div class="square" :style="{ backgroundColor: color }"></div>
</template>

<script>
export default {
  props: ["color"],
};
</script>

<style>
.square {
  width: 100px;
  height: 100px;
  border-radius: 5px;
  box-shadow: 1px 1px 20px rgba(0,0,0,0.2);
}

.square:hover {
  width: 110px;
  height: 110px;
}
</style>
