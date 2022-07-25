<template>
  <section class="webinar-block-all">
    <div class="container">
      <div class="webinar">
        <div class="webinar-header">
          <h2 id="Webinar">Live Online Webinar</h2>
          <p>You can stream Webinar live on our apps. Stay update on our Webinar, it’s Free!</p>
        </div>
        <div class="webinar-block">
          <div class="webinar-block-video1">
            <a href="https://www.youtube.com/embed/sohdv21BVNI" rel="noopener, noreferrer, nofollow" title="Google Play" target="_blank">
              <img src="../assets/img/s4/foto1-s4.png" alt="illustration">
            </a>
          </div>
          <div class="webinar-block-video2">
            <a href="https://www.youtube.com/embed/H0FuxfHDFlQ" rel="noopener, noreferrer, nofollow" title="Google Play" target="_blank">
              <img src="../assets/img/s4/foto2-s4.png" alt="illustration"></a>
          </div>
          <div class="webinar-block-video3">
            <a href="https://www.youtube.com/embed/iPdEp3WhdpA" rel="noopener, noreferrer, nofollow" title="Google Play" target="_blank">
              <img src="../assets/img/s4/foto3-s4.png" alt="illustration">
            </a>
          </div>
        </div>
        <div class="webinar-reference">
          <a href="https://www.youtube.com/results?search_query=programming" rel="noopener, noreferrer, nofollow" title="Google Play" target="_blank">See more webinar videos</a>
          <img src="../assets/img/s4/arrow-right-s4.png" alt="illustration">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'webinar-block',
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

.webinar-block-all {
  padding-top: 85px;
  padding-bottom: 80px;
}
.webinar {
  .webinar-header {
    margin: 0 auto;
    width: 672px;
    h2 {
      font-size: 36px;
      line-height: 54px;
      color: $headings-text;
      margin: 0 auto 20px;
      text-align: center;
    }
    p {
      font-size: 18px;
      line-height: 27px;
      margin-bottom: 195px;
    }
  }
  .webinar-block {
    display: flex;
    justify-content: space-between;
    position: relative;
    margin-bottom: 113px;
    .webinar-block-video1 {
      width: 34%;
    }
    .webinar-block-video2 {
      position: absolute;
      top: -34%;
      left: 24%;
      width: 52%;
    }
    .webinar-block-video3 {
      width: 34%;
    }
  }
  .webinar-reference {
    display: flex;
    justify-content: end;
    a {
      color: $text-color2;
      font-size: 14px;
      margin-right: 20px;
      &:hover {
        color: $text-button;
      }
    }
    img {
      width: 24px;
      height: 32px;
      padding-top: 1px;
    }
  }
}

@media screen and (max-width: 1360px){
  .webinar .webinar-header h2 {
    font-size: 36px;
    line-height: 54px;
    text-align: center;
  }
  .webinar .webinar-header p {
    font-size: 18px;
    line-height: 27px;
    text-align: center;
  }
  .webinar {
    .webinar-header {
      h2 {
        margin: 0 auto 20px;
      }
      p {
        margin: 0 auto 140px;
      }
    }
    .webinar-block {
      flex-wrap: wrap;
      .webinar-block-video1 {
        width: 40%;
      }
      .webinar-block-video2 {
        position: absolute;
        top: -15%;
        left: 26%;
        width: 50%;
      }
      .webinar-block-video3 {
        width: 40%;
      }
    }
  }
}

@media screen and (max-width: 1120px){
  .webinar {
    .webinar-header {
      width: 300px;
    }
    .webinar-block {
      flex-wrap: wrap;
      .webinar-block-video1 {
      }
      .webinar-block-video2 {
        position: absolute;
        top: -15%;
        left: 27%;
        width: 49%;
      }
    }
  }
}

@media screen and (max-width: 990px){
  .webinar-block-all {
    padding-top: 60px;
    padding-bottom: 55px;
  }
  .webinar {
    .webinar-block {
      flex-wrap: wrap;
      margin-bottom: 60px;
      .webinar-block-video1 {
      }
      .webinar-block-video2 {
        position: absolute;
        top: -15%;
        left: 27%;
        width: 46%;
      }
      .webinar-block-video3 {
      }
    }
  }
}

@media screen and (max-width: 768px){
  .webinar .webinar-header h2 {
    font-size: 20px;
    line-height: 45px;
  }
  .webinar .webinar-header p {
    font-size: 16px;
    line-height: 24px;
  }
  .webinar {
    .webinar-header {
      p {
        text-align: center;
        width: 325px;
        margin: 10px auto 60px;
      }
    }
    .webinar-block {
      flex-wrap: wrap;
      .webinar-block-video1 {
      }
      .webinar-block-video2 {
        position: absolute;
        top: -15%;
        left: 26%;
        width: 45%;
      }
      .webinar-block-video3 {
      }
    }
    .webinar-reference {
      img {
        width: 22px;
        height: 27px;
        padding-top: 4px;
      }
    }
  }
}

@media screen and (max-width: 600px){
  .webinar {
    .webinar-header {
      h2 {
        width: 300px;
      }
      p {
        text-align: center;
        width: 300px;
        margin: 10px auto 60px;
      }
    }
    .webinar-block {
      flex-wrap: wrap;
      .webinar-block-video1 {
      }
      .webinar-block-video2 {
        position: absolute;
        top: -15%;
        left: 27%;
        width: 45%;
      }
      .webinar-block-video3 {
      }
    }
    .webinar-reference {
      padding-right: 8px;
      img {
        width: 22px;
        height: 27px;
        padding-top: 4px;
      }
      a {
        font-size: 12px;
      }
    }
  }
}

@media screen and (max-width: 320px){
  .webinar-block-all {
    padding-bottom: 40px;
  }
}

</style>