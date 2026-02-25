<template>
  <div>
<h1>My shop</h1>
<div class="container">
  <div v-for="cloth in clothes" :key="cloth.name">
<h2>{{ cloth.name }}</h2>
<h2>{{ cloth.price }}</h2>
<h2>{{ cloth.inStock }}</h2>
<h2>{{ cloth.brand }}</h2>
<h2>{{ cloth.alt }}</h2>
<img :src="cloth.img" alt="">
<button>Buy ME</button>
  </div>
</div>
  </div>
</template>

<script setup>
const clothes =[
    {
        name: "Sponge bob cleats",
        price: 119.99,
        inStock: true,
        brand: "Sponge bob",
        img: "https://phenomelitebrand.com/cdn/shop/files/SpongebobProductShot4_535x.png?v=1740765484",
        alt: "Cleats",
    },
        {
        name: "Ukrainian Jersey",
        price: 34.99,
        inStock: true,
        brand: "Adidas",
        img: "/116401-removebg-preview.png",
        alt: "Jersey",
    },    
           {
        name: "2022 World Cup Soccer Ball",
        price: 39.99,
        inStock: true,
        brand: "Adidas",
        img: "/hd-qatar-world-cup-2022-ball-png-7040816948791863showibkng-removebg-preview.png",
        alt: "Soccer ball",
    },        {
        name: "Cleats",
        price: 89.99,
        inStock: true,
        brand: "Nike",
        img: "/imgbin-nike-mercurial-vapor-football-boot-cleat-nike-FeKUXXVBpwvUrZ9cpgQUxBzrz-removebg-preview.png",
        alt: "Nike cleats",
    },        {
        name: "Soccer ball",
        price: 19.99,
        inStock: true,
        brand: "Generic",
        img: "/1000_F_190984838_0fvehfxAtlLrwREWAYkS0pmZknmHlA7c-removebg-preview.png",
        alt: "Soccer ball",
    },       
     {
        name: "Barcelona Jersey",
        price: 34.99,
        inStock: true,
        brand: "Nike",
        img: "/5bc1a53012e3b-removebg-preview.png",
        alt: "Jersey",
    },     {
        name: "Goalkeeping gloves",
        price: 34.99,
        inStock: true,
        brand: "Adidas",
        img: "img/images-removebg-preview.png",
        alt: "gloves",
    },        {
        name: "U.S. Jersey",
        price: 34.99,
        inStock: true,
        brand: "Nike",
        img: "/third-jersey-united-states-men-s-national-soccer-team-shirt-kit-shirt-removebg-preview.png",
        alt: "Jersey",
    },       {
    name: "Liverpool Jersey",
    price: 34.99,
    inStock: true,
    brand: "New Balance",
    img: "/t-shirt-liverpool-f-c-jersey-kit-t-shirt-removebg-preview.png",
    alt: "Jersey",
  },
  {
    name: "Soccer ball",
    price: 29.99,
    inStock: true,
    brand: "Nike",
    img: "/soccer-ball-hk1099-premier-league-winter-ball-2018-19-11563421364hwhip7iy4d-removebg-preview.png",
    alt: "Soccer ball",
  },
  {
    name: "Barcelona shorts",
    price: 14.99,
    inStock: true,
    brand: "Nike",
    img: "/avuw9xoqg-removebg-preview.png",
    alt: "shorts",
  },
  {
    name: "Black shorts",
    price: 9.99,
    inStock: true,
    brand: "Generic",
    img: "/ITAM_Essential_AthleticShorts_Black-removebg-preview.png",
    alt: "shorts",
  },
  {
    name: "White shorts",
    price: 9.99,
    inStock: true,
    brand: "Generic",
    img: "/mockup-of-a-white-sports-pant-free-png-removebg-preview.png",
    alt: "shorts",
  },    
  {
  name: "Golden cleats",
  price: 199.99,
  inStock: true,
  brand: "Nike",
  img: "https://png.pngtree.com/png-vector/20250112/ourmid/pngtree-golden-football-cleat-clipart-illustration-png-image_15160443.png",
  alt: "Cleats",
},
{
  name: "MLS ball",
  price: 9.99,
  inStock: true,
  brand: "Adidas",
  img: "/seo-gifts-for-soccer-fans-body-image-1_221-578642-removebg-preview.png",
  alt: "Soccer ball",
},
{
  name: "Orange and white cleats",
  price: 99.99,
  inStock: true,
  brand: "Generic",
  img: "/pngtree-durable-soccer-cleats-for-outdoor-games-png-image_13451541-removebg-preview.png",
  alt: "Cleats",
},
{
  name: "Blue gloves",
  price: 9.99,
  inStock: true,
  brand: "Nike",
  img: "/275-2754018_goal-keeping-glove-png-photo-background-nike-goalkeeper-removebg-preview.png",
  alt: "Gloves",
},
{
  name: "Red shorts",
  price: 15.99,
  inStock: true,
  brand: "Adidas",
  img: "/461686s-removebg-preview.png",
  alt: "Shorts",
},
{
  name: "Red gloves",
  price: 9.99,
  inStock: true,
  brand: "Adidas",
  img: "/pngtree-red-goalkeeper-gloves-png-image_16215402-removebg-preview.png",
  alt: "Gloves",
},
{
  name: "Blue and yellow gloves",
  price: 9.99,
  inStock: true,
  brand: "Kipsta",
  img: "/620-6206722_goal-keeping-glove-png-transparent-image-kipsta-goalkeeper-removebg-preview.png",
  alt: "Gloves",
},   
];

</script>

<style scoped>
html, body, *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-size: 62.5%; /* Normally 100% is 16px we want the size to be 10px so we do 62.5% */
}
.container{
    font-size: 30px;
    display: flex;
    background-color: wheat;
    justify-content: space-around;
    width: 100vw;
    flex-wrap: wrap;
}
.display-card{
     width:22%;
     display: flex;
     flex-direction: column;
     align-items: center;
     justify-content: space-around;
}
.display-img{
    width: 100%;
}
.cart-section {
    font-size: 35px;
    justify-content: space-around;
    text-align: center;
    background-color: orange;
}

</style>