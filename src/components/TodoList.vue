<template>
  <div>
    <p
        v-for="(item, index) in list"
        :class="{'done': item.status}"
        :key="item.value"
        @click="toggleList(index)"
    >
        {{item.value}}
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: this.todoData, // dont direct modify the data from parent, sign to a child variable.
    };
  },
  methods: {
    toggleList(index) {
      // this.toggleList[index].status = !this.toggleList(index).status
      // this.$set(this.list[index], 'status', !this.list[index].status);
      this.list[index].status = !this.list[index].status;
    },
  },
  props: ['todoData'], // decalre this child will received a props from parent.
};
</script>

<style>
.done{
    background-color: yellow;
}
</style>
