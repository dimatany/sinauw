<template>
  <section class="classes-block-all">
    <div class="container">
      <div class="classes">
        <div class="classes-header">
          <h2 id="Courses">What Do You Want to Learn?</h2>
          <p>Choose the right class as you need. Then enjoy studying.</p>
        </div>
        <div class="classes-card">
          <div class="classes-card-item" v-for="(classes, index) in classesBlockData" :key="index">
            <img :src="require('@/assets/img/s3/' +classes.img)" :alt="classes.title">
            <p class="classes-card-item-count">{{ classes.number }}</p>
            <span class="classes-card-item-title">{{ classes.title }}</span>
            <h4>{{ classes.subtitle }}</h4>
            <p>{{ classes.text }}</p>
            <div class="classes-card-footer">
              <div class="classes-card-footer-avatar">
                <img :src="require('@/assets/img/s3/' +classes.avatar)" :alt="classes.title">
              </div>
              <div class="classes-card-footer-name">
                <span class="name">{{ classes.name }}</span>
                <span class="position">{{ classes.position }}</span>
              </div>
            </div>
            <div class="classes-card-button">
              <button type="submit" name="button" title="button">Access class</button>
            </div>
          </div>
        </div>
        <div class="classes-button">
          <button>Show All Classes</button>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
export default {
  name: 'classes-block',

  data () {
    return {
      classesBlockData: []
    }
  },
  created() {
    axios
    .get('../data/classes-block.json')
    .then (resp => {
      this.classesBlockData = resp.data
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

.classes-block-all {
  padding-top: 84px;
  padding-bottom: 86px;
}
.classes {
  .classes-header {
    margin: 0 auto;
    text-align: center;
    h2 {
      font-size: 36px;
      line-height: 54px;
      color: $headings-text;
      margin-bottom: 19px;
    }
    p {
      font-size: 18px;
      line-height: 27px;
      margin-left: 3px;
      margin-bottom: 85px;
    }
  }
  .classes-card {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 120px;
    .classes-card-item {
      width: 276px;
      padding: 10px;
      border: 3px solid #282B57;
      border-radius: 15px;
      background-color: $highlighting-elements4;
      position: relative;
      &:hover {
        .classes-card-button {
          height: 43px;
        }
      }
      img {
        width: 252px;
        height: 169px;
        border-radius: 13px;
        margin-bottom: 21px;
      }
      .classes-card-item-count {
        padding: 4px;
        background: $highlighting-elements6;
        border-radius: 8px;
        width: 88px;
        font-size: 12px;
        color: $text-button;
        position: absolute;
        top: 139px;
        left: 20px;
      }
      .classes-card-item-title {
        display: block;
        color: $headings-text3;
        font-weight: 500;
        font-size: 12px;
        margin-bottom: 7px;
      }
      h4 {
        font-size: 18px;
        color: $headings-text;
        margin-bottom: 12px;
      }
      p {
        font-size: 14px;
        line-height: 22px;
        padding-bottom: 20px;
        border-bottom: 1px solid $highlighting-elements2;
        margin-bottom: 16px;
      }
      .classes-card-footer {
        display: flex;
        margin-bottom: -10px;
        .classes-card-footer-avatar img {
          width: 40px;
          height: 40px;
          border-radius: 50%;
        }
        .classes-card-footer-name {
          display: flex;
          flex-direction: column;
          margin-left: 15px;
          .name {
            font-weight: 500;
            font-size: 14px;
            color: $headings-text;
          }
          .position {
            font-size: 12px;
          }
        }
      }
      .classes-card-button {
        overflow: hidden;
        transition: all .4s ease-in;
        text-align: center;
        height: 0;
        button {
          width: 155px;
          padding: 12px 32px;
          background-color: $highlighting-elements;
          border-radius: 6px;
          font-size: 14px;
          line-height: 17px;
          font-weight: 600;
          color: $headings-text;
          border: 1px solid transparent;
          &:hover {
            margin: 0 auto;
            display: block;
            border: 1px solid $focus-color;
            box-shadow:inset 0 0 15px 3px rgba(17, 37, 93, 1);
            background:linear-gradient(rgba(208, 2, 27, 1), rgba(208, 2, 27, 1));
          }
        }
      }
    }
  }
  .classes-button {
    width: 200px;
    margin: 0 auto;
    button {
      width: 198px;
      padding: 16px 32px;
      border: 1px solid $highlighting-elements;
      border-radius: 6px;
      font-weight: 700;
      font-size: 15px;
      line-height: 19px;
      color: $highlighting-elements;
      &:hover {
        border: 1px solid $focus-color;
        box-shadow:inset 0 0 15px 3px rgba(0, 0, 0, 1);
      }
    }
  }
}

@media screen and (max-width: 1360px){
  .classes .classes-header h2 {
    font-size: 36px;
    line-height: 54px;
    text-align: center;
  }
  .classes .classes-header p {
    font-size: 18px;
    line-height: 27px;
    text-align: center;
  }
  .classes {
    .classes-header {
      margin: 0 20px 0;
      h2 {
        margin-left: 0;
      }
      p {
        margin-bottom: 75px;
      }
    }
    .classes-card {
      justify-content: space-evenly;
      flex-wrap: wrap;
      margin: 0 50px 40px 50px;
      .classes-card-item {
        padding: 20px;
        margin: 40px;
        img {
          margin-left: -10px;
        }
        .classes-card-item-count {
          top: 139px;
          left: 20px;
        }
        .classes-card-item-title {
        }
        h4 {
          font-size: 18px;
        }
        p {
          font-size: 16px;
        }
        .classes-card-footer {
          .classes-card-footer-avatar img {
          }
          .classes-card-footer-name {
            .name {

            }
            .position {

            }
          }
        }
        .classes-card-button {
          button {
          }
        }
      }
    }
    .classes-button {
      button {

      }
    }
  }
}

@media screen and (max-width: 990px){
  .classes-block-all {
    padding-top: 59px;
    padding-bottom: 59px;
  }
}

@media screen and (max-width: 768px){
  .classes .classes-header h2 {
    font-size: 20px;
    line-height: 45px;
  }
  .classes .classes-header p {
    font-size: 16px;
    line-height: 24px;
  }
  .classes {
    .classes-header {
      h2 {
        text-align: center;
      }
      p {
        margin-bottom: 20px;
        text-align: center;
      }
    }
    .classes-card {
      justify-content: space-evenly;
      flex-wrap: wrap;
      .classes-card-item {
        padding: 20px;
        margin: 40px;
        img {
          margin-left: -10px;
        }
        .classes-card-item-count {
          top: 139px;
          left: 20px;
        }
        .classes-card-footer {
          .classes-card-footer-avatar img {
          }
          .classes-card-footer-name {
            .name {
            }
            .position {

            }
          }
        }
      }
    }
  }
}

@media screen and (max-width: 500px){
  .classes {
    .classes-card {
      justify-content: space-evenly;
      flex-wrap: wrap;
      .classes-card-item {
        padding: 20px;
        min-width: 260px;
        img {
          width: 240px;
          margin-left: -10px;
        }
        .classes-card-item-count {
          top: 139px;
          left: 20px;
        }
      }
    }
    .classes-button {
      width: 160px;
      button {
        margin: 0 auto;
        width: 160px;
        padding: 10px 10px;
      }
    }
  }
}

@media screen and (max-width: 320px){
  .classes-block-all {
    padding-top: 40px;
  }
}

</style>