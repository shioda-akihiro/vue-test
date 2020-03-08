<template>
  <div>
    <h1>{{ msg }}</h1>
    <counter />
    <item-list />
  </div>
</template>

<script>
import counter from "./counter.vue";
import ItemList from "./ItemList.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    counter,
    ItemList
  }
};
</script>
