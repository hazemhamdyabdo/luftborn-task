<script setup></script>

<template>
  <figure class="person">
    <figcaption class="person-bg">
      <img src="/Bitmap.png" alt="Person Pic" class="person-bg-pic" />
      <div class="person-bg-text">
        <p class="person-bg-text-reporter">Reporter for</p>
        <h2 class="person-bg-text-title">Best Sales</h2>
      </div>
    </figcaption>
    <div class="person-timezone">
      <ul class="person-timezone-list">
        <li>Daily</li>
        <li>Weekly</li>
        <li>Monthly</li>
      </ul>
    </div>
  </figure>
</template>

<style lang="scss" scoped>
.person {
  // width: 16rem;
  // flex-shrink: 0;
  height: 32.3rem;
  position: relative;

  &-bg {
    // width: 255px;
    // height: 324px;
    // flex-shrink: 0;
    background-color: #5747ea;
    border-radius: 15px;
    padding-top: 20px;

    &-pic {
      border-radius: 50%;
      border: 3px solid #fff;
      box-shadow: -2px 14px 29px -8px rgba(0, 0, 0, 0.445);
      display: block;
      margin: 0 auto;
      // width: 138px;
      // height: 145px;
      // flex-shrink: 0;
    }
    &-text {
      display: flex;
      flex-direction: column;
      padding-left: 1.3rem;
      width: 208px;
      height: 152px;
      // flex-shrink: 0;
      padding-top: 1rem;

      &-reporter {
        color: #bbc0ff;
        font-size: 15px;
        font-style: normal;
        font-weight: 400;
        line-height: normal;
      }

      &-title {
        font-size: 40px;
        font-style: normal;
        font-weight: 300;
        line-height: normal;
        letter-spacing: 12px;
        margin-top: 0.5rem;
      }
    }
  }

  &-timezone {
    background: #1c204b;
    display: flex;
    position: absolute;
    z-index: -1;
    bottom: 1rem;
    border-radius: 15px;
    width: 100%;

    &-list {
      height: 13rem;
      padding-left: 1.3rem;
      padding-top: 1rem;
      list-style: none;
      color: #7078c9;
      font-family: Rubik;
      font-size: 18px;
      font-style: normal;
      font-weight: 400;
      line-height: normal;
      display: flex;
      flex-direction: column;
      justify-content: center;
      gap: 1rem;
      text-align: left;

      & :nth-child(2) {
        color: #fff;
      }
    }
  }
}

@media only screen and (max-width: 545px) {
  .person {
    height: 15rem;
    width: 400px;
    margin-left: -3rem;
    margin-bottom: 1rem;
    &-bg {
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1rem;

      &-pic {
        width: 5rem;
        margin: auto 0;
      }
      &-text {
        width: 100%;
        justify-content: center;

        &-title {
          line-height: 1;
          letter-spacing: 2px;
          font-size: 2rem;
        }
      }
    }

    &-timezone {
      bottom: 0rem;
      &-list {
        display: flex;
        flex-direction: row;
        align-items: flex-end;
        padding-bottom: 1rem;
        padding-left: 4rem;
        justify-content: space-between;
        gap: 4rem;
      }
    }
  }
}
</style>
