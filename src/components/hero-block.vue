<template>
  <section class="hero-block-all">
    <div class="container">
      <div class="hero-section">
        <div class="hero-section-avatar">
          <img src="../assets/img/s1/avatar-s1.png" alt="logo">
          <div class="hero-section-avatar-position">
            <img src="../assets/img/s1/lamp-s1.png" alt="icon">
            <img src="../assets/img/s1/book-s1.png" alt="icon">
          </div>
        </div>
        <div class="hero-section-description" v-for="(hero, index) in heroBlockData" :key="index">
          <div class="hero-section-description-info">
            <h1>{{ hero.title }}</h1>
            <p>{{ hero.text }}</p>
            <form class="search-container">
              <input type="text" id="search-bar" placeholder="What do you want to learn...">
              <a href="#">
                <img class="search-icon" src="../assets/img/s1/search.svg" alt="logo">
              </a>
            </form>
          </div>
          <div class="hero-section-description-suggestions">
            <p>{{ hero.subtitle }}</p>
            <div class="hero-section-description-suggestions-block1">
              <a href="#"><button type="button">{{ hero.suggestions1 }}</button></a>
              <a href="#"><button type="button">{{ hero.suggestions2 }}</button></a>
              <a href="#"><button type="button">{{ hero.suggestions3 }}</button></a>
            </div>
            <div class="hero-section-description-suggestions-block2">
              <a href="#"><button type="button">{{ hero.suggestions4 }}</button></a>
              <a href="#"><button type="button">{{ hero.suggestions5 }}</button></a>
              <a href="#"><button type="button">{{ hero.suggestions6 }}</button></a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'
export default {
  name: 'hero-block',
  data () {
    return {
      heroBlockData: []
    }
  },
  created() {
    axios
    .get('../data/hero-block.json')
        .then (resp => {
          this.heroBlockData = resp.data
    })
  }
};
</script>


<style lang="scss" scoped>

$background-color: #171836;
$background-color-element: #282B57;
$headings-text: rgba(255, 255, 255, 0.8);
$headings-text2: rgba(255, 255, 255, 0.7);
$headings-text3: rgba(59, 245, 189, 1);
$text-color: rgba(255, 255, 255, 0.4);
$text-color2: rgba(255, 255, 255, 0.6);
$text-color3: rgba(209, 209, 215, 1);
$text-color4: rgba(143, 145, 208, 1);
$text-button: rgba(255, 255, 255, 1);
$highlighting-elements: rgba(245, 68, 59, 1);
$highlighting-elements2: rgba(41, 43, 86, 1);
$highlighting-elements3: rgba(151, 153, 206, 1);
$highlighting-elements4: #212145;
$highlighting-elements5: #4c4567;
$highlighting-elements6: rgba(255, 255, 255, 0.2);
$icon-color: #ACABBF;
$focus-color: #008ABF;
$border-color: rgba(154, 156, 203, 0.6);

.hero-block-all {
  padding-top: 120px;
  padding-bottom: 104px;
}
.hero-section {
  display: flex;
  justify-content: space-between;
  padding-bottom: 127px;
  .hero-section-avatar {
    position: relative;
    img {
      width: 695px;
      height: 682px;
    }
    .hero-section-avatar-position {
      img:nth-child(1){
        position: absolute;
        top: 22%;
        right: 90%;
        max-width: 90px;
        max-height: 90px;
        border-radius: 20px;
        background-color: $background-color-element;
        padding: 13px;
        transform: rotate(-8deg);
      }
      img:nth-child(2){
        position: absolute;
        top: 7%;
        right: 23%;
        max-width: 90px;
        max-height: 90px;
        border-radius: 20px;
        background-color: $background-color-element;
        padding: 13px;
        transform: rotate(12deg);
      }
    }
  }
  .hero-section-description {
    padding: 93px 0 0 0;
    max-width: 506px;
    .hero-section-description-info {
      h1 {
        font-size: 56px;
        //font-size: clamp(1rem, 5vw + 1rem, 3.5rem);
        line-height: 73px;
        color: $headings-text;
        word-spacing: -4px;
        margin-bottom: 24px;
      }
      p {
        font-size: 18px;
        line-height: 27px;
        margin-bottom: 56px;
      }
      .search-container {
        position: relative;
        margin-bottom: 48px;
        input#search-bar{
          width: 506px;
          height: 68px;
          padding: 0 32px;
          background-color: #1F2143;
          border-radius: 8px;
          &:focus{
            border: 1px solid $focus-color;
            transition: 0.35s ease;
            color: $highlighting-elements;
            &::placeholder {
              transition: opacity 0.45s ease;
              opacity: 0;
            }
          }
          &:hover{
            box-shadow: inset 5px -5px 10px #13141a, inset -5px 5px 10px #333644;
          }
        }
        .search-icon{
          position: absolute;
          width: 24px;
          height: auto;
          top: 32%;
          right: 4%;
        }
      }
    }
    .hero-section-description-suggestions {
      p {
        font-weight: 400;
        line-height: 27px;
        margin-bottom: 34px;
      }
      button {
        padding: 5px 17px;
        border: 1px solid $border-color;
        font-size: 14px;
        border-radius: 8px;
        margin-right: 5px;
        &:focus{
          border: 1px solid $focus-color;
          transition: 0.35s ease;
          color: $highlighting-elements;
        }
        &:hover{
          box-shadow: inset 5px -5px 10px #13141a, inset -5px 5px 10px #333644;
          transition: 0.35s ease;
          color: $highlighting-elements;
        }
      }
      .hero-section-description-suggestions-block1 {
        margin-bottom: 25px;
        display: flex;
        justify-content: space-between;
      }
      .hero-section-description-suggestions-block2 {
        max-width: 465px;
        display: flex;
        justify-content: space-between;
        align-items: center;
      }
    }
  }
}

@media screen and (max-width: 1360px){
  .hero-section .hero-section-description .hero-section-description-info h1{
    font-size: 50px;
    line-height: 67px;
    text-align: center;
  }
  .hero-section .hero-section-description .hero-section-description-info p {
    font-size: 16px;
    text-align: center;
  }
  .hero-section {
    padding-bottom: 0;
    .hero-section-avatar {
      position: relative;
      margin-top: 95px;
      img {
        width: 525px;
        height: 590px;
      }
      .hero-section-avatar-position {
        img:nth-child(1){
          top: 20%;
          right: 83%;
          max-width: 70px;
          max-height: 70px;
        }
        img:nth-child(2){
          top: 6%;
          right: 17%;
          max-width: 70px;
          max-height: 70px;
        }
        img:nth-child(3){
          top: 75%;
          right: 7%;
        }
      }
    }
    .hero-section-description {
      padding: 94px 0 0 0;
      max-width: 506px;
      .hero-section-description-info {
        margin: 0 20px 0;
        .search-container {
          input#search-bar{
            width: 445px;
            height: 60px;
            margin-left: 8px;
          }
          .search-icon{
            position: absolute;
            float: right;
            width: 24px;
            height: auto;
            top: 36%;
            right: 9%;
          }
        }
      }
      .hero-section-description-suggestions {
        display: flex;
        justify-content: space-evenly;
        p {
          display: none;
          margin-right: 10px;
        }
        button {
          width: 200px;
          height: 50px;
          margin-bottom: 20px;
        }
        .hero-section-description-suggestions-block1 {
          display: flex;
          flex-direction: column;
          height: 210px;
        }
        .hero-section-description-suggestions-block2 {
          display: flex;
          flex-direction: column;
          height: 210px;
        }
      }
    }
  }
}

@media screen and (max-width: 1120px){
  .hero-section {
    display: flex;
    flex-wrap: wrap;
    .hero-section-avatar {
      position: relative;
      margin: 0 auto 0;
      img {
        width: 525px;
        height: 590px;
      }
      .hero-section-avatar-position {
        img:nth-child(1){
          position: absolute;
          top: 35%;
          right: 88%;
          max-width: 90px;
          max-height: 90px;
        }
        img:nth-child(2){
          position: absolute;
          top: 23%;
          right: -9%;
          max-width: 90px;
          max-height: 90px;
        }
      }
    }
    .hero-section-description {
      width: 720px;
      margin: -60px auto;
      .hero-section-description-info {
        .search-container {
          input#search-bar{
            height: 60px;
            margin-left: 8px;
          }
          .search-icon{
            top: 36%;
            right: 9%;
          }
        }
      }
      .hero-section-description-suggestions {
        display: flex;
        justify-content: space-evenly;
        button {
          width: 200px;
          height: 50px;
          margin-bottom: 20px;
        }
        .hero-section-description-suggestions-block1 {
          display: flex;
          flex-direction: column;
          height: 210px;
        }
        .hero-section-description-suggestions-block2 {
          display: flex;
          flex-direction: column;
          height: 210px;
        }
      }
    }
  }
}

@media screen and (max-width: 990px){
  .hero-block-all {
    padding-top: 82px;
    padding-bottom: 45px;
  }
}

@media screen and (max-width: 768px){
  .hero-section .hero-section-description .hero-section-description-info h1{
    font-size: 25px;
    line-height: 50px;
  }
  .hero-section .hero-section-description .hero-section-description-info p {
    font-size: 14px;
  }
  .hero-section {
    display: flex;
    flex-wrap: wrap;
    .hero-section-avatar {
      position: relative;
      margin: 0 auto 0;
      img {
        width: 460px;
        height: auto;
      }
      .hero-section-avatar-position {
        img:nth-child(1){
          position: absolute;
          top: 37%;
          right: 83%;
          max-width: 60px;
          max-height: 60px;
        }
        img:nth-child(2){
          position: absolute;
          top: 25%;
          right: 0;
          max-width: 60px;
          max-height: 60px;
        }
      }
    }
    .hero-section-description {
      max-width: 506px;
      margin: -60px auto;
      .hero-section-description-info {
        .search-container {
          input#search-bar{
            height: 60px;
            margin-left: 8px;
          }
          .search-icon{
            top: 36%;
            right: 9%;
          }
        }
      }
      .hero-section-description-suggestions {
        display: flex;
        justify-content: space-evenly;
        p {
          display: none;
          margin-right: 10px;
        }
        button {
          width: 200px;
          height: 50px;
          margin-bottom: 20px;
        }
        .hero-section-description-suggestions-block1 {
          display: flex;
          flex-direction: column;
          height: 210px;
        }
        .hero-section-description-suggestions-block2 {
          display: flex;
          flex-direction: column;
          height: 210px;
        }
      }
    }
  }
}

@media screen and (max-width: 500px){
  .hero-section {
    display: flex;
    flex-wrap: wrap;
    .hero-section-avatar {
      position: relative;
      margin: 0 auto 0;
      img {
        width: 280px;
      }
      .hero-section-avatar-position {
        img:nth-child(1){
          position: absolute;
          top: 35%;
          right: 77%;
          max-width: 50px;
          max-height: 50px;
        }
        img:nth-child(2){
          position: absolute;
          top: 17%;
          right: -1%;
          max-width: 50px;
          max-height: 50px;
        }
      }
    }
    .hero-section-description {
      margin: -60px auto;
      .hero-section-description-info {
        .search-container {
          margin: -10px auto 30px;
          max-width: 260px;
          input#search-bar{
            width: 260px;
            height: 60px;
            margin: 0 auto;
            &::placeholder {
              font-size: 13px;
            }
          }
          .search-icon{
            top: 34%;
            right: 8%;
            width: 20px;
          }
        }
      }
      .hero-section-description-suggestions {
        display: flex;
        flex-wrap: wrap;
        p {
          display: none;
          margin-right: 10px;
        }
        button {
          width: 200px;
          height: 50px;
          margin-bottom: 20px;
          font-size: 11px;
        }
        .hero-section-description-suggestions-block1 {
          display: flex;
          flex-direction: column;
        }
        .hero-section-description-suggestions-block2 {
          display: flex;
          flex-direction: column;
          width: 100%;
        }
      }
    }
  }
}

@media screen and (max-width: 320px){
  .hero-section {
    display: flex;
    flex-wrap: wrap;
    .hero-section-avatar {
      position: relative;
      margin: 0 auto 0;
      img {
        max-width: 260px;
      }
      .hero-section-avatar-position {
        img:nth-child(1){
          position: absolute;
          top: 35%;
          right: 77%;
          max-width: 50px;
          max-height: 50px;
        }
        img:nth-child(2){
          position: absolute;
          top: 15%;
          right: -1%;
          max-width: 50px;
          max-height: 50px;
        }
      }
    }
    .hero-section-description {
      margin: -60px auto;
      .hero-section-description-info {
        .search-container {
          margin: -10px auto 30px;
          max-width: 280px;
          input#search-bar{
            max-width: 280px;
            height: 60px;

          }
          .search-icon{
            top: 36%;
            right: 5%;
          }
        }
      }
      .hero-section-description-suggestions {
        display: flex;
        flex-wrap: wrap;
        p {
          display: none;
          margin-right: 10px;
        }
        button {
          width: 200px;
          height: 50px;
          margin-bottom: 20px;
        }
        .hero-section-description-suggestions-block1 {
          display: flex;
          flex-direction: column;
        }
        .hero-section-description-suggestions-block2 {
          display: flex;
          flex-direction: column;
          width: 100%;
        }
      }
    }
  }
}

</style>