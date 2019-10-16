<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{message}}</p>
    <p v-bind:title="message1">Test v-bind function</p>
    <input type="bool" v-model="message1">
    <br>
    <p v-if="true">Weather is good</p>
    <span @click="res">{{message}}</span>

    <p v-for="(item, index) in list"
       :key = item
    >
    {{item}} {{index}}
    </p>

  </div>
</template>


<script>
export default {
  data() {
    return {
      message: 'Good Morning, Jason !!!',
      message1: `New Zealand${new Date().toLocaleDateString}`,
      list: ['123', '456', '789'],
      bool: true,
    };
  },
  methods: {
    getInfor() {
      alert(this.message);
    },
    res() {
      this.message = this.message.split('').reverse().join('');
    },
  },
  mounted() {
    setTimeout(() => {
      this.bool = false;
    }, 3000);
  },
};
</script>
