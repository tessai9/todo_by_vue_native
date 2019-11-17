<template>
  <view class="container">
    <view class="navbar">
      <text style="{font-size: 35; font-weight: bold;}">To Do</text>
    </view>
    <view class="register">
      <text-input class="register_title" v-model="input_title" placeholder="input todo title" />
      <text-input class="register_content" v-model="input_cont"  placeholder="input todo content" />
      <button
        :on-press="add_todo"
        title="Register!"
        style="{ width: 60; height: 20; font-size: 15; margin-top: 10; }"
      />
    </view>
    <text style="{ font-size: 30; font-weight: bold; margin-top: 15; }">登録したToDo</text>
    <view
      v-for="item in todos"
    >
        <text class="list_title">{{ item.title }}</text>
        <text class="list_cont">{{ item.content }}</text>
    </view>
  </view>
</template>

<script>
import {Alert} from 'react-native';
export default {
  data: function () {
    return {
      todos: [],
      input_title: "",
      input_cont: ""
    }
  },
  methods: {
    add_todo: function() {
      this.todos.push({ title: this.input_title, content: this.input_cont })
      this.input_title = ""
      this.input_cont = ""
    }
  }
}
</script>

<style>
.container {
  align-items: center;
  flex: 1;
}
.navbar {
  background-color: #1E90FF;
  text-align: center;
  top: 0;
  width: 100%;
  height: 60;
}
.register {
  margin-top: 15;
}
.register_title,
.register_content {
  font-size: 20;
}
.list_title {
  font-size: 25;
  font-weight: bold;
}
.list_cont {
  font-size: 15;
}
</style>
