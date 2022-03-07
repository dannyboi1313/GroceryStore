<template>
<div class="cart">
  <h1>Your Cart</h1>
  <h2 v-if="empty" class="empty">Cart Empty</h2>
  <CartList :products="cart" v-else />
</div>
</template>

<script>
import CartList from "../components/CartList.vue"
export default {
  name: 'cart-view',
  components: {
    CartList
  },
  data() {
    return {
    }
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    },
    total(){
        return this.$root.$data.cart.length;
    },
    empty(){
        return (this.$root.$data.cart.length == 0);
    }

  },
  methods: {
  }
}
</script>

<style scoped>
    .cart{
        background-color: #F0F0F0;
        text-align: center;
        color:#B84901;
    }

    .empty{
        color:#D8DAD0;
    }
    

</style>