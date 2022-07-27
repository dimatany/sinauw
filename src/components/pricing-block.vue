<template>
  <section class="pricing-block-all">
    <div class="container">
      <div class="pricing">
        <div class="pricing-header">
          <h2 id="Prising">Course Pricing</h2>
          <p>Choose pricing that suits to your need.</p>
        </div>
        <div class="pricing-block">
          <div class="pricing-block-item" v-for="(pricing, index) in pricingBlockData" :key="index">
            <div class="pricing-block-item-header">
              <div class="pricing-block-item-header-stick">
                <img :src="require('@/assets/img/s5/' +pricing.img)" :alt="pricing.title">
              </div>
              <div class="pricing-block-item-header-tariffs">
                <div class="pricing-block-item-header-tariffs-name">
                  <span>{{ pricing.title }}</span>
                </div>
                <div class="pricing-block-item-header-tariffs-price">
                  <span class="sign">{{ pricing.currency }}</span>
                  <span class="price">{{ pricing.price }}</span>
                  <span class="period">{{ pricing.period }}</span>
                </div>
              </div>
            </div>
            <div class="pricing-block-item-info">
              <ul>
                <li>{{ pricing.condition1 }}</li>
                <li>{{ pricing.condition2 }}</li>
                <li>{{ pricing.condition3 }}</li>
                <li>{{ pricing.condition4 }}</li>
                <li v-if="pricing.condition5 !== '' ">{{ pricing.condition5 }}</li>
                <li v-if="pricing.condition6 !== '' ">{{ pricing.condition6 }}</li>
                <li v-if="pricing.condition7 !== '' ">{{ pricing.condition7 }}</li>
              </ul>
            </div>
            <div class="sub-btn">
              <button>{{ pricing.submit1 }}</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
  name: 'pricing-block',
  data () {
    return {
      pricingBlockData: []
    }
  },
  created() {
    axios
    .get('../data/pricing-block.json')
    .then (resp => {
      this.pricingBlockData = resp.data
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

.pricing-block-all {
  padding-top: 80px;
  padding-bottom: 87px;
}
.pricing {
  .pricing-header {
    margin: 0 auto;
    width: 330px;
    h2 {
      font-size: 36px;
      line-height: 54px;
      color: $headings-text;
      width: 257px;
      margin: 0 auto 20px;
    }
    p {
      font-size: 18px;
      line-height: 27px;
      margin-bottom: 84px;
      text-align: center;
    }
  }
  .pricing-block {
    display: flex;
    justify-content: space-between;
    .pricing-block-item {
      border: 3px solid $background-color-element;
      border-radius: 20px;
      padding: 33px;
      background-color: $highlighting-elements4;
      display: flex;
      flex-direction: column;
      .pricing-block-item-header {
        display: flex;
        border-bottom: 1px solid rgb(41, 43, 86);
        padding-bottom: 24px;
        margin-bottom: 15px;
        .pricing-block-item-header-exception {
          position: relative;
          img {
            width: 99px;
            height: 92px;
            position: absolute;
            top: -36px;
            left: 237px;
            border-radius: 20px;
          }
        }
        .pricing-block-item-header-stick {
          margin: 2px 29px 0 1px;
          img {
            height: 56px;
          }
        }
        .pricing-block-item-header-tariffs {
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          height: 67px;
          .pricing-block-item-header-tariffs-name {
            padding-top: 3px;
            color: $headings-text;
            font-weight: 600;
            font-size: 18px;
          }
          .pricing-block-item-header-tariffs-price {
            display: flex;
            height: 34px;
            .sign {
              display: flex;
              align-items: flex-start;
              height: 100%;
              color: $highlighting-elements;
              margin-right: 3px;
            }
            .price {
              color: $highlighting-elements;
              font-size: 28px;
              display: flex;
              align-items: center;
              height: 100%;
              margin-right: 5px;
            }
            .period {
              color: $headings-text;
              font-size: 11px;
              font-weight: 500;
              display: flex;
              align-items: flex-end;
              height: 100%;
            }
          }
        }
      }
      .pricing-block-item-info {
        margin-left: -7px;
        flex: 1 1 auto;
        padding-bottom: 33px;
        ul {
          li {
            color: $headings-text;
            font-size: 14px;
            line-height: 17px;
            transition: all .3s ease-in;
            padding: 10px;
            &:before {
              content: "";
              margin-right: 7px;
              list-style-type: circle;
              display: inline-block;
              width: 10px;
              height: 10px;
              border-radius: 50%;
              background: #9799ce;
            }
          }
        }
      }
      .sub-btn {
        button {
          width: 300px;
          border: 1px solid $highlighting-elements;
          border-radius: 6px;
          color: $highlighting-elements;
          height: 50px;
          &:hover {
            color: $headings-text;
            background-color: $highlighting-elements;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 1360px){
  .pricing .pricing-header h2 {
    font-size: 36px;
    line-height: 54px;
    text-align: center;
  }
  .pricing .pricing-header p {
    font-size: 18px;
    line-height: 27px;
    text-align: center;
  }
  .pricing {
    .pricing-header {
      h2 {
        width: 200px;
      }
      p {
        margin: -7px 15px 40px;
      }
    }
    .pricing-block {
      flex-wrap: wrap;
      .pricing-block-item {
        padding: 62px;
        margin: 0 auto 30px;
        .pricing-block-item-header {
          .pricing-block-item-header-exception {
            img {
              width: 103px;
              top: -64px;
              left: 262px;
            }
          }
          .pricing-block-item-header-stick {
            img {
              height: 36px;
            }
          }
          .pricing-block-item-header-tariffs {
            flex-direction: column;
            .pricing-block-item-header-tariffs-name {
              font-size: 16px;
            }
            .pricing-block-item-header-tariffs-price {
              .sign {
              }
              .price {
                font-size: 20px;
              }
              .period {
              }
            }
          }
        }
        .pricing-block-item-info {
          ul {
            li {
            }
          }
        }
        .sub-btn {
          button {
            height: 50px;
          }
        }
        .pricing-block-item-sub1 {

        }
        .pricing-block-item-sub2 {

        }
        .pricing-block-item-sub3 {

        }
      }
    }
  }
}

@media screen and (max-width: 990px){
  .pricing-block-all {
    padding-top: 55px;
    padding-bottom: 60px;
  }
}

@media screen and (max-width: 768px){
  .pricing .pricing-header h2 {
    font-size: 20px;
    line-height: 45px;
  }
  .pricing .pricing-header p {
    font-size: 16px;
    line-height: 24px;
  }
  .pricing {
    .pricing-header {
      h2 {
        width: 200px;
      }
      p {
      }
    }
    .pricing-block {
      flex-wrap: wrap;
      .pricing-block-item {
        padding: 30px;
        margin: 0 auto 30px;
        .pricing-block-item-header {
          .pricing-block-item-header-exception {
            img {
              width: 92px;
              top: -32px;
              left: 170px;
              height: 85px;
            }
          }
          .pricing-block-item-header-stick {
            img {
              height: 36px;
            }
          }
          .pricing-block-item-header-tariffs {
            flex-direction: column;
            .pricing-block-item-header-tariffs-name {
              font-size: 16px;
            }
          }
        }
        .sub-btn {
          margin: 55px 20px 0 18px;
          button {
            height: 50px;
            width: 190px;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 500px){
  .pricing {
    .pricing-header {
      width: 300px;
    }
    .pricing-block {
      .pricing-block-item {
        padding: 10px;
        margin: 0 auto 30px;
        .pricing-block-item-header {
          .pricing-block-item-header-exception {
            img {
              width: 81px;
              top: -13px;
              left: 179px;
              height: 75px;
            }
          }
          .pricing-block-item-header-stick {
            img {
              height: 36px;
              padding-top: 12px;
              padding-left: 12px;
            }
          }
          .pricing-block-item-header-tariffs {
            flex-direction: column;
            .pricing-block-item-header-tariffs-name {
            }
          }
        }
        .pricing-block-item-sub1 {
          padding: 10px 10px;
        }
        .pricing-block-item-sub2 {
          padding: 10px 10px;
        }
        .pricing-block-item-sub3 {
          padding: 10px 10px;
        }
      }
    }
  }
}

</style>