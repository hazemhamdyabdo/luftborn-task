<script setup>
defineProps(["data", "colors"]);
</script>
<template>
  <section class="product" v-for="(item, index) in data" :key="item.div">
    <div style class="product-cover">
      <div
        class="product-cover-pic"
        :style="`background-color: ${colors[index]}`"
      >
        &nbsp;
      </div>
      <!-- <img :src="images[index]" alt="color gameped" class="product-cover-pic" /> -->
    </div>
    <div class="product-info">
      <div class="product-info-title">
        <h3>{{ item.category }}</h3>
        <img src="/Combined-Shape.svg" alt="Dots" />
      </div>
      <p class="product-info-price">{{ item.price }}$</p>
      <div class="product-info-store">
        <p>{{ item.description }}</p>
        <p>
          inSore
          <br />
          {{ item.rating.count }}
        </p>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.product {
  position: relative;

  &-cover-pic {
    width: 255px;
    height: 160px;
    flex-shrink: 0;
    // background: v-bind(colors);
    border-radius: 15px;
  }

  &-info {
    border-radius: 15px;
    background: #1c204b;
    position: absolute;
    z-index: 2;
    top: 2.5rem;
    left: -0.1rem;
    width: 258px;
    height: 196px;
    // flex-shrink: 0;
    display: flex;
    flex-direction: column;
    padding: 2.2rem 1.8rem;

    &-title {
      display: flex;
      justify-content: space-between;
      margin-bottom: 2rem;

      & h3 {
        font-family: Rubik;
        font-size: 18px;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
      }

      & img {
        cursor: pointer;
      }
    }
    &-price {
      font-size: 39px;
      font-style: normal;
      font-weight: 300;
      line-height: normal;
      margin-bottom: 0.4rem;
    }
    &-store {
      color: #bbc0ff;
      font-size: 12px;
      font-style: normal;
      font-weight: 400;
      line-height: normal;
      display: flex;
      gap: 1rem;

      & p:first-child {
        width: 300px;
        display: -webkit-box;
        -webkit-box-orient: vertical;
        -webkit-line-clamp: 2;
        overflow: hidden;
      }

      & p:last-child {
        color: #fff;
        font-size: 12px;
        font-style: normal;
        font-weight: 500;
        line-height: normal;
        text-align: center;
      }
    }
  }
}

@media only screen and (max-width: 545px) {
  .product {
    margin-top: 2rem;
    &-cover {
      width: 24.8rem;
      margin-left: -3rem;
      &-pic {
        width: 100%;
      }
    }

    &-info {
      margin-left: -3rem;
      width: 400px;
      top: 2.5rem;
      left: -0.1rem;
      padding: 2.2rem 1.8rem;
      height: 10rem;

      &-title {
        margin-bottom: 0.4rem;
      }
      &-price {
        font-size: 3rem;
      }
      &-store {
        & p:first-child {
          position: absolute;
          bottom: 3.5rem;
          right: 0rem;
          width: 12rem;
        }
        & p:last-child {
          display: none;
        }
      }
    }
  }
}
</style>
