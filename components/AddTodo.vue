<template>
  <view>
    <view>
      <text-input
        class="input"
        placeholder="New todo..."
        v-model="newTodoText"
      />
      <Button title="ADD" :on-press="newTodo" />
    </view>
    <touchable-opacity
      v-for="todo in todos"
      :key="todo.id"
      :on-press="() => deleteTodo(todo.id)"
    >
      <view class="item">
        <MaterialIcons name="delete-forever" size="25" color="black" />
        <text class="itemText">{{ todo.text }}</text>
      </view>
    </touchable-opacity>
  </view>
</template>

<script>
import { MaterialIcons } from '@expo/vector-icons';
import { Alert } from 'react-native';
export default {
  components: {
    MaterialIcons,
    Alert,
  },
  data() {
    return {
      newTodoText: '',
      todos: [
        { text: 'Finnish todo app', id: '1' },
        { text: 'Start TicTacToe app', id: '2' },
        { text: 'Play with my son', id: '3' },
      ],
    };
  },
  methods: {
    newTodo() {
      if (this.newTodoText.length > 3) {
        console.log(this.todos);
        console.log(this.task);
        this.todos.push({
          text: this.newTodoText,
          id: Math.random().toString(),
        });
        this.newTodoText = '';
        console.log(this.todos);
      } else {
        Alert.alert(
          'ERROR!!',
          'The todo must have more than 3 characters DUDE!!!',
          [{ text: 'Okidoki', onPress: () => console.log('alert closed') }]
        );
      }
    },
    deleteTodo(id) {
      return (this.todos = this.todos.filter((todo) => todo.id != id));
    },
  },
};
</script>

<style>
.input {
  margin-bottom: 10;
  padding: 10;
  border-bottom-width: 1;
  border-bottom-color: #ddd;
}
.item {
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 16;
  margin-top: 16;
  border-color: #bbb;
  border-width: 1;
  border-style: dashed;
  border-radius: 15;
}
.itemText {
  padding-left: 10;
}
</style>
