<template>
  <div class="container mx-auto px-6 lg:pt-12 lg:px-20 grid grid-cols-1 lg:grid-cols-10 col-gap-10 row-gap-10 pb-8 lg:pb-24">
    <Payment @change-parent="handleAlert" :total="total"></Payment>
    <Sumary :items="items"></Sumary>
    <Alert :visible="alertVisible" position="top-right" color="success" title="Success" description="Your payment has been successfully processed." />
  </div>
</template>

<script>
import Payment from "../components/Payment";
import Sumary from "../components/Sumary";
import Alert from "../components/Alert";

export default {
  name: "CheckoutPage",
  components: {
    Payment,
    Sumary,
    Alert
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
      alertVisible: false,
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
    },
    handleAlert() {
      this.alertVisible = true;
      setTimeout(() => {
        this.alertVisible = false;
      }, 4000);
    }
  }
};
</script>
