<template>
  <div id="app">
    <div id="nav">
      <h1>Shop</h1>
      <h3 class="openCart">Cart({{cartItems}})</h3>
      <div class="cart">
        <div class="itemList">
          <Item
          @remove="removeItem()"
          v-for="(inCart, index) in inCart"
          :id="`${i}`"
          :key="index"
          :name="inCart.name"
          :price="`$${inCart.price}`"
          :image="inCart.image"
          />
        </div>
        <h4>{{cartItems}} Items in Cart</h4>
        <h4>Subtotal: ${{subtotal}}</h4>
      </div>
    </div>
    <section class="display">
      <Card 
      @add="addCart(index)"
      v-for="(item, index) in items"
      :key="index" 
      :id="`${i}`"
      :name="`${item.name} (${item.artist})`" 
      :price="`$${item.price}`" 
      :image="item.image"
      />
    </section>
  </div>
</template>

<script>

import Card from "./components/Card.vue"
import Item from "./components/Item.vue"

export default {
  components: {
    Card, Item
  },
  data(){
    return {
      cartButton: `Cart`,
      cartItems: 0,
      subtotal: 0,
      cartPrice: [],
      inCart: [],
      items: [
  // rock
  {
    name: "Tattoo You",
    artist: "The Rolling Stones",
    genre: "Rock",
    year: 1981,
    price: 28,
    image: "https://upload.wikimedia.org/wikipedia/en/1/16/TattooYou81.jpg",
  },
  {
    name: "Ten",
    artist: "Pearl Jam",
    genre: "Rock",
    year: 1991,
    price: 28,
    image: "https://upload.wikimedia.org/wikipedia/en/2/2d/PearlJam-Ten2.jpg",
  },
  {
    name: "Nevermind",
    artist: "Nirvana",
    genre: "Rock",
    year: 1991,
    price: 32,
    image: "https://upload.wikimedia.org/wikipedia/en/b/b7/NirvanaNevermindalbumcover.jpg",
  },
  {
    name: "Ok Computer",
    artist: "Radiohead",
    genre: "Rock",
    year: 1997,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/b/ba/Radioheadokcomputer.png",
  },
  {
    name: "Stadium Arcadium",
    artist: "Red Hot Chili Peppers",
    genre: "Rock",
    year: 2006,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/e/e6/Stadiumarcadium.jpg",
  },
  // r&b
  {
    name: "Confessions",
    artist: "Usher",
    genre: "RNB",
    year: 2004,
    price: 22,
    image: "https://upload.wikimedia.org/wikipedia/en/7/74/Usher_-_Confessions_album_cover.jpg",
  },
  {
    name: "Destiny Fulfilled",
    artist: "Destiny's Child",
    genre: "RNB",
    year: 2004,
    price: 28,
    image: "https://upload.wikimedia.org/wikipedia/en/2/22/Destiny%27s_Child_%E2%80%93_Destiny_Fulfilled.jpg",
  },
  {
    name: "Channel Orange",
    artist: "Frank Ocean",
    genre: "RNB",
    year: 2012,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/2/28/Channel_ORANGE.jpg",
  },
  {
    name: "Trapsoul",
    artist: "Bryson Tiller",
    genre: "RNB",
    year: 2015,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/4/4e/Trapsoulalbum.jpeg",
  },
  {
    name: "Blonde",
    artist: "Frank Ocean",
    genre: "RNB",
    year: 2016,
    price: 26,
    image: "https://upload.wikimedia.org/wikipedia/en/a/a0/Blonde_-_Frank_Ocean.jpeg",
  },
  {
    name: "Ctrl",
    artist: "SZA",
    genre: "RNB",
    year: 2017,
    price: 22,
    image: "https://upload.wikimedia.org/wikipedia/en/b/bf/SZA_-_Ctrl_cover.png",
  },
  // rap
  {
    name: "Illmatic",
    artist: "Nas",
    genre: "Rap",
    year: 1994,
    price: 27,
    image: "https://upload.wikimedia.org/wikipedia/en/2/27/IllmaticNas.jpg",
  },
  {
    name: "The College Dropout",
    artist: "Kanye West",
    genre: "Rap",
    year: 2004,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/a/a3/Kanyewest_collegedropout.jpg",
  },
  {
    name: "Madvillainy",
    artist: "MF Doom",
    genre: "Rap",
    year: 2004,
    price: 34,
    image: "https://upload.wikimedia.org/wikipedia/en/5/5e/Madvillainy_cover.png",
  },
  {
    name: "Tha Carter III",
    artist: "Lil Wayne",
    genre: "Rap",
    year: 2008,
    price: 24,
    image: "https://upload.wikimedia.org/wikipedia/en/c/c8/CarterIII.jpg",
  },
  {
    name: "Live. Love. A$AP",
    artist: "A$AP Rocky",
    genre: "Rap",
    year: 2011,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/e/eb/Live_Love_ASAP.jpg",
  },
  {
    name: "1999",
    artist: "Joey Bada$$",
    genre: "Rap",
    year: 2012,
    price: 23,
    image: "https://upload.wikimedia.org/wikipedia/en/5/56/1999_Joey_Badass.jpg",
  },
  {
    name: "2014 Forest Hills Drive",
    artist: "J. Cole",
    genre: "Rap",
    year: 2014,
    price: 30,
    image: "https://upload.wikimedia.org/wikipedia/en/2/2a/2014ForestHillsDrive.jpg",
  },
  {
    name: "To Pimp a Butterfly",
    artist: "Kendrick Lamar",
    genre: "Rap",
    year: 2015,
    price: 32,
    image: "https://upload.wikimedia.org/wikipedia/en/f/f6/Kendrick_Lamar_-_To_Pimp_a_Butterfly.png",
  },
  {
    name: "Coloring Book",
    artist: "Chance the Rapper",
    genre: "Rap",
    year: 2016,
    price: 26,
    image: "https://upload.wikimedia.org/wikipedia/en/c/c4/Chance_the_Rapper_-_Coloring_Book.png",
  },
  // classics
  {
    name: "Thriller",
    artist: "Michael Jackson",
    genre: "Classics",
    year: 1982,
    price: 36,
    image: "https://upload.wikimedia.org/wikipedia/en/5/55/Michael_Jackson_-_Thriller.png",
  },
  {
    name: "The Queen is Dead",
    artist: "The Smiths",
    genre: "Classics",
    year: 1986,
    price: 33,
    image: "https://upload.wikimedia.org/wikipedia/en/e/ed/The-Queen-is-Dead-cover.png",
  },
  {
    name: "Doolittle",
    artist: "Pixies",
    genre: "Classics",
    year: 1989,
    price: 25,
    image: "https://upload.wikimedia.org/wikipedia/en/6/6b/Pixies-Doolittle.jpg",
  },
  {
    name: "Loveless",
    artist: "My Bloody Valentine",
    genre: "Classics",
    year: 1991,
    price: 24,
    image: "https://upload.wikimedia.org/wikipedia/en/4/4b/My_Bloody_Valentine_-_Loveless.png",
  },
],
    }
  },
  methods: {
    addCart(index) {
      this.inCart.push(this.items[index])
      this.cartPrice.push(this.items[index].price)
      this.subtotal = this.subtotal + this.items[index].price
      this.cartItems = this.cartItems + 1
    },
    removeItem() {
      this.inCart.pop();
      this.subtotal = this.subtotal - this.cartPrice[this.cartPrice.length - 1]
      this.cartItems = this.cartItems - 1
    }
  }
}
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #151515;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  #nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 4rem;
    position: sticky;
    background-color: white;
    top: 0;
    z-index: 2;
  }

  #nav a {
    font-weight: bold;
    color: #151515;
    text-decoration: none;
  }

  #nav a.router-link-exact-active {
    color: #999999;
    text-decoration: none;
  }

  .display {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }

  .openCart {
    z-index: 1;
  }

  .openCart:hover {
    cursor: pointer;
    text-decoration: underline;
  }

  .openCart:hover ~ .cart {
    display: block;
  }

  .cart:hover {
    display: block;
  }

  .cart {
    display: none;
    position: fixed;
    top: 0;
    right: 0;
    padding-top: 5rem;
    width: 22rem;
    background-color: #fff;
    z-index: 0;
    transition: 0.3s;
  }

</style>
