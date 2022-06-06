<template>
  <header>
    <h3>{{ msg }} hello</h3>
  </header>

  <div class="container">
    <h3>Credit Card Input</h3>
    <credit-card
      v-model:nameOnCard="nameOnCard"
      v-model:cardNumber="cardNumber"
      v-model:expiry="expiry"
      v-model:cvv="cvv"
    ></credit-card>
    <br />
    <hr />
    <p>Name : {{ nameOnCard }}</p>
    <p>cardNumber : {{ cardNumber }}</p>
    <p>expiry : {{ expiry }}</p>
    <p>CVV : {{ cvv }}</p>
  </div>
</template>

<script>
import CreditCard from "./CreditCard.vue";
export default {
  data() {
    return {
      msg: "Vue3 Vite Project",
      nameOnCard: "Mr.",
      cardNumber: "",
      expiry: "",
      cvv: "",
    };
  },
  methods: {},
  components: {
    CreditCard,
  },
};
</script>
