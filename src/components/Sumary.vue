<template>
  <div class="col-span-1 lg:col-span-4">
    <h4 class="text-3xl text-gray-700 mb-5">Order Sumary</h4>
    <div class="p-10 rounded-md shadow-md bg-white">
      <item :key="i" v-for="(item, i) in items"/>
    </div>
  </div>
</template>

<script>
import Item from "./Item";
export default {
  name: "Sumary",
  components: {
    Item
  },
  data() {
    return {
      items: [1, 1, 1]
    };
  }
};
</script>
