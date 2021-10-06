<template>
  <view class="container">
    <Banner />
    <view class="content">
      <AddTodo />
        <!-- <TodoItem /> -->
      <view class="list">
        <flat-list
        >
      </view>
    </view>
  </view>
</template>

<script>
import Banner from './components/Banner.vue';
import AddTodo from './components/AddTodo.vue';
import TodoItem from './components/TodoItem.vue';

export default {
  components: {
    Banner,
    AddTodo,
    TodoItem,
  },
  
};
</script>

<style>
.container {
  flex: 1;
  background-color: #fff;
}
.content {
  padding: 40;
  flex: 1;
}
.list {
  margin-top: 20;
  flex: 1;
}
</style>
