<template>
  <div class="container mx-auto px-6 lg:pt-12 lg:px-20 grid grid-cols-1 lg:grid-cols-10 col-gap-10 row-gap-24">
    <Payment></Payment>
    <Sumary></Sumary>
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
  }
};
</script>
