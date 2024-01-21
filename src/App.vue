<script setup>
import MainPerson from "./components/MainPerson.vue";
import ProductItem from "./components/ProductItem.vue";
import { onMounted, ref } from "vue";
const data = ref([]);
const fetchedDate = async () => {
  const request = await fetch("https://fakestoreapi.com/products?limit=10");
  const response = await request.json();
  console.log(response);
  data.value = response;
};

const colors = ref([
  "#FF8B64",
  "#55C2E6",
  "#FF5E7D",
  "#FF8B64",
  "#55C2E6",

  "#4BCF82",
  "#7335D2",
  "#F1C75B",
  "#4BCF82",
  "#7335D2",
]);
onMounted(() => {
  fetchedDate();
});
</script>

<template>
  <main class="main">
    <div class="container">
      <MainPerson class="person" />
      <ProductItem :data="data" :colors="colors" />
    </div>
  </main>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Rubik";
}

body {
  background-color: #0e1323;
  color: #fff;
}
.main {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 10%;
}
.container {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: repeat(2, 1fr);
  grid-column-gap: 20px;
  grid-row-gap: 15px;

  & .person {
    grid-row: 1 / span 2;
  }
}

@media only screen and (max-width: 1350px) {
  .container {
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(4, 1fr);
    grid-column-gap: 15px;
    grid-row-gap: 1px;

    & .person {
      grid-row: 1 / span 2;
    }
  }
}
@media only screen and (max-width: 800px) {
  .container {
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: repeat(7, 1fr);
    grid-column-gap: 15px;
    grid-row-gap: 1px;

    & .person {
      grid-row: 1 / span 2;
    }
  }
}
@media only screen and (max-width: 545px) {
  .container {
    grid-template-columns: repeat(1, 1fr);
    grid-template-rows: repeat(11, 1fr);
    grid-column-gap: 0rem;
    grid-row-gap: 0px;

    & .person {
      grid-row: 1 / span 1;
    }
  }
}
</style>
