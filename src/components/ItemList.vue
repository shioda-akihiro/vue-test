<template>
  <div>
    <div>ItemList</div>
    <div v-for="item in items" :key="item.name">
      <div class="item">
        <div class="item" :class="{over500: item.value >= 500}">
            <div class="name">名前: {{ item.name }}</div>
            <div class="price">{{ item.value }} 円</div>
        </div>
      </div>
    </div>
    <div>
      <label>
        名前
        <input type="text" v-model="newItemName">
      </label>
      <label>
        価格
        <input type="number" v-model="newItemValue">
      </label>
      <button @click="addItem">add</button>
    </div>
  </div>
</template>

<style>
.over500{
    color: red;
}
</style>

<script>
export default {
  name: "ItemList",
  data() {
    return {
      items: [{ name: "egg", value: 100 }, { name: "apple", value: 160 }],
      newItemName: "",
      newItemValue: 0
    };
  },
  methods: {
    addItem() {
      this.items.push({ name: this.newItemName, value: this.newItemValue });
    }
  }
};
</script>