<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{message}}</p>
    <!-- test v-bind, howover your mouse -->
    <p v-bind:title="message1">Test v-bind function</p>
    <!-- redirection model -->
    <input type="text" v-model="message">
    <!-- test bool  -->
    <p v-if="bool">Weather is good</p>
    <br>
    <!-- function to reverse the string -->
    <span @click="res">{{message}}</span>
    <p @click="getInfo">enter value</p>
    <br>
    <p v-for="(item, index) in list"
       :key = item
    >
    {{item}} {{index}}
    </p>
    <br>
    <!-- pass the props call todoData to the compoent, the value is list in the parent -->
    <todo-list
    :todoData="todoItemList"
    >
    </todo-list>
  </div>
</template>


<script>
import TodoList from '@/components/TodoList.vue';


export default {
  components: {
    TodoList,
  },
  data() {
    return {
      message: 'Good Morning, Jason !!!',
      message1: `New Zealand${new Date().toLocaleString()}`,
      list: ['123', '456', '789'],
      todoItemList: [{
        value: '123',
        status: false,
      }, {
        value: '456',
        status: false,
      }, {
        value: '789',
        status: false,
      }],
      bool: true,
    };
  },
  methods: {
    getInfo() {
      alert(this.message);
    },
    res() {
      alert('i been hit');
      this.message = this.message.split('').reverse().join('');
    },
  },
  // it will set the bool to false after 5s, so will render the dom
  mounted() {
    // setTimeout(() => {
    //   this.list.push('jason is testing props');
    // }, 3000);
    setTimeout(() => {
      this.bool = false;
    }, 5000);
  },
};
</script>
