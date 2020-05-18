<template>
  <div class="container mx-auto px-6 lg:pt-12 lg:px-20 grid grid-cols-1 lg:grid-cols-10 col-gap-10 row-gap-10 pb-8 lg:pb-24">
    <Payment :total="total"></Payment>
    <Sumary :items="items"></Sumary>
  </div>
</template>

<script>
import Payment from "../components/Payment";
import Sumary from "../components/Sumary";

export default {
  name: "CheckoutPage",
  components: {
    Payment,
    Sumary
  },
  data() {
    return {
      items: [
        {
          title: "Title 1",
          description: "lorem impsu liwe",
          price: 550
        },
        {
          title: "Title 2",
          description: "lorem impsu liwe",
          price: 250
        },
        {
          title: "Title 3",
          description: "lorem impsu liwe",
          price: 150
        }
      ],
      total: 0
    };
  },
  mounted() {
    this.getTotal(this.items);
  },
  methods: {
    getTotal(items) {
      items.forEach(item => {
        this.total += item.price;
      });
    }
  }
};
</script>
