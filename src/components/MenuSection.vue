<template>
    <section>
        <div>
            <button @click="filterItems('all')">All</button>
            <button @click="filterItems('coffee')">Coffee</button>
            <button @click="filterItems('cocktails')">Cocktails</button>
            <button @click="filterItems('cake')">Cake</button>
            <button @click="filterItems('fast food')">Fast Food</button>
            <button @click="filterItems('snacks')">Snacks</button>
        </div>
        <div class="menu-item" v-for="item in filteredItems" :key="item.id">
            <img :src="item.image" alt="Menu Item">
            <div>{{ item.name }}</div>
            <div>{{ item.price }}</div>
        </div>
    </section>
  </template>
  
  <script>
  export default {
    data() {
      return {
        menuItems: [
          { id: 1, name: 'Coffee 1', category: 'coffee', price: '$2.50', image: './assets/item-img-1.png' },
          { id: 2, name: 'Cocktail 1', category: 'cocktails', price: '$8.00', image: './assets/item-img-12.png' },
          { id: 3, name: 'Cake 1', category: 'cake', price: '$4.50', image: './assets/item-img-2.png' },
          { id: 4, name: 'Chinese soup', category: 'fast food', price: '$4.50', image: './assets/item-img-6.png' },
          { id: 5, name: 'Coca Cola', category: 'cocktails', price: '$5.00', image: './assets/item-img-10.png' },
          { id: 6, name: 'Sandwitch', category: 'fast food', price: '$3.00', image: './assets/item-img-5.png' },
          { id: 7, name: 'French Fries', category: 'snacks', price: '$3.00', image: './assets/item-img-4.png' },
          { id: 8, name: 'Burger', category: 'fast food', price: '$3.00', image: './assets/item-img-3.png' },
          { id: 9, name: 'coffee 2', category: 'coffee', price: '$3.00', image: './assets/item-img-8.png' },
          // Add more menu items here
        ],
        selectedCategory: 'all'
      };
    },
    computed: {
      filteredItems() {
        if (this.selectedCategory === 'all') return this.menuItems;
        return this.menuItems.filter(item => item.category === this.selectedCategory);
      }
    },
    methods: {
      filterItems(category) {
        this.selectedCategory = category;
      }
    }
  }
  </script>
  
  <style>
  section{
    width: 90%;
    margin: 0 auto;
  }
  button{
    background-color: transparent;
    color: #fff;
    font-family: 'Poppins', sans-serif;
    border: none;
    cursor: pointer;
    font-size: 1.2rem;
  }
  button:hover  {
    color: #FFC492;
  }
  .menu-item {
    width: 30%;
    float: left;
    padding: 10px;
    box-sizing: border-box;
    margin: 10px;
  }
  .menu-item{
    cursor: pointer;
  }
  </style>
  