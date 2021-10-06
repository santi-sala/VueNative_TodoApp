<template>
  <touchable-opacity>
    <view class="item">
      <MaterialIcons name="delete-forever" size="25" color="black" />
      <text class="itemText">Que pasa</text>
    </view>
  </touchable-opacity>
</template>

<script>
import { MaterialIcons } from '@expo/vector-icons';
export default {
  components: { MaterialIcons },
};
</script>

<style>
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
