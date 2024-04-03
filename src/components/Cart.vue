<template>
    <div>
      <h2>Shopping Cart</h2>
      <div v-for="cartItem in cartItems" :key="cartItem.id">
        <p>{{ cartItem.name }} - Quantity: {{ cartItem.quantity }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cartItems: []
      };
    },
    methods: {
      addToCart(item) {
      
        const existingItem = this.cartItems.find(cartItem => cartItem.id === item.id);
  
        if (existingItem) {
          existingItem.quantity += 1;
        } else {
          this.cartItems.push({
            id: item.id,
            name: item.name,
            quantity: 1
          });
        }
      }
    },
    components: {
   
    }
  };
  </script>
  
  <style scoped>

  </style>