<template>
  <section class="featured-block-all">
    <div class="container">
      <div class="featured" >
        <div class="featured-block" v-for="(featured, index) in featuredBlockData" :key="index">
          <div class="featured-icon">
            <img :src="require('@/assets/img/s2/' +featured.img)" :alt="featured.title">
            <h4>{{ featured.title }}</h4>
          </div>
          <div class="featured-text">
            <p>{{ featured.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
export default {
  name: 'featured-block',
  data () {
    return {
      featuredBlockData: []
    }
  },
  created() {
    axios
    .get('../data/featured-block.json')
    .then (resp => {
      this.featuredBlockData = resp.data
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

.featured-block-all {
  padding-top: 82px;
  padding-bottom: 65px;
}
.featured {
  display: flex;
  justify-content: space-between;
  .featured-block {
    .featured-icon {
      display: flex;
      align-items: center;
      img {
        margin-right: 17px;
        width: 65px;
        //height: 24px;
      }
      h4 {
        color: $headings-text2;
        font-weight: 600;
        font-size: 20px;
      }
    }
    .featured-text {
      margin-top: 27px;
      margin-left: 60px;
      p {
        max-width: 311px;
        font-size: 14px;
        line-height: 24px;
        font-weight: 400;
        color: $text-color2;
      }
    }
  }
}

@media screen and (max-width: 1360px){
  .featured .featured-block .featured-icon h4 {
    font-size: 20px;
    text-align: center;
  }
  .featured .featured-block .featured-text p {
    line-height: 20px;
    text-align: center;
  }
  .featured {
    .featured-block {
      .featured-icon {
        img {
          margin-right: 0;
          width: 50px;
        }
      }
      .featured-text {
        p {
          margin-left: -19px;
          max-width: 211px;
        }
      }
    }
  }
}

@media screen and (max-width: 990px){
  .featured-block-all {
    padding-top: 44px;
    padding-bottom: 59px;
  }
}

@media screen and (max-width: 768px){
  .featured .featured-block .featured-icon h4 {
    font-size: 16px;
  }
  .featured .featured-block .featured-text p {
    font-size: 14px;
    line-height: 18px;
    text-align: center;
  }
  .featured {
    display: flex;
    flex-wrap: wrap;
    margin: 0 auto 0;
    padding-right: 20px;
    max-width: 400px;
    .featured-block {
      .featured-icon {
        margin: 60px auto -10px;
        display: flex;
        justify-content: center;
      }
      .featured-text {
        p {
          margin-left: -19px;
          max-width: 400px;
          text-align: center;
        }
      }
    }
  }
}

@media screen and (max-width: 320px){
  .featured-block-all {
    padding-bottom: 40px;
  }
}

</style>