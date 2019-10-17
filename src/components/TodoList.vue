<template>
  <div>
    <p v-for="item in todoData" :key="item">{{item}}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: [12, 11, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1],
    };
  },
  props: ['todoData'],
};
</script>

<style>

</style>
