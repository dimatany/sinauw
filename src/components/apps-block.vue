<template>
  <section class="apps-block-all">
    <div class="container">
      <div class="apps">
        <div class="apps-info">
          <h3>Get Our Apps, Now!</h3>
          <p>Reach out our apps everywhere and everytime with Sinauw Mobile Application.</p>
          <div class="apps-info-brands">
            <div class="apps-info-brands-google">
              <a href="https://play.google.com/store/apps" rel="noopener, noreferrer, nofollow" title="Google Play" target="_blank">
                <img src="../assets/img/s6/google-s6.png" alt="illustration">
              </a>
            </div>
            <div class="apps-info-brands-apple">
              <a href="https://www.apple.com/ua/app-store/" rel="noopener, noreferrer, nofollow" title="App Store" target="_blank">
                <img src="../assets/img/s6/apple-s6.png" alt="illustration">
              </a>
            </div>
          </div>
        </div>
        <div class="apps-visual">
          <div class="apps-visual-card">
            <div class="apps-visual-card-header">
              <div class="apps-visual-card-header-avatar">
                <img src="../assets/img/s6/Man-s6.svg" alt="icon">
              </div>
              <div class="apps-visual-card-header-description">
                <p class="hello">Hello, Alexander</p>
                <p class="member">Premium Member</p>
              </div>
              <div class="apps-visual-card-header-res">
                <img src="../assets/img/s5/corona-icon.svg" alt="icon">
              </div>
              <div class="apps-visual-card-header-avatar1">
                <img src="../assets/img/s6/avatar1-s6.png" alt="avatar">
              </div>
            </div>
            <div class="apps-visual-card-body">
              <div class="apps-visual-card-body-icon">
                <img src="../assets/img/s6/lamp-s6.svg" alt="icon">
              </div>
              <div class="apps-visual-card-body-description">
                <p class="header-text">Grow Your Skill, Join Now!</p>
                <p class="descr-text">We have something big for you who want to level up!</p>
              </div>
              <div class="apps-visual-card-body-avatar2">
                <img src="../assets/img/s6/avatar2-s6.png" alt="avatar">
              </div>
              <div class="apps-visual-card-body-avatar3">
                <img src="../assets/img/s6/avatar3-s6.png" alt="avatar">
              </div>
              <div class="apps-visual-card-body-ref">
                <div class="apps-visual-ref-course">
                  <img src="../assets/img/s6/fa-solid-s6.png" alt="icon">
                  <p>Courses Progress<i class="right"></i></p>
                </div>
                <div class="apps-visual-ref-class">
                  <img src="../assets/img/s6/fa-solid_lapt-s6.png" alt="icon">
                  <p>Class Collections<i class="right"></i></p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'apps-block',
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

.apps-block-all {
  padding-top: 87px;
  padding-bottom: 70px;
}
.apps {
  display: flex;
  justify-content: space-between;
  padding: 70px 137px 70px 70px;
  border-radius: 40px;
  //background-color: $highlighting-elements4;
  background: url("@/assets/img/s6/wp.jpg") center/cover;
  position: relative;
  z-index: 1;
  overflow: hidden;
  animation: hue 15s infinite alternate;
  .apps-info {
    padding-top: 16px;
    padding-left: 31px;
    h3 {
      font-size: 47px;
      color: $text-button;
      line-height: 75px;
      margin-bottom: 12px;
      text-align: center;
    }
    p {
      width: 406px;
      font-size: 18px;
      color: $headings-text2;
      line-height: 32px;
      margin-bottom: 40px;
    }
    .apps-info-brands {
      display: flex;
      justify-content: space-between;
      width: 342px;
      padding-left: 5px;
      .apps-info-brands-google {
        img {
          width: 165px;
          height: 55px;
        }
      }
      .apps-info-brands-apple {
        img {
          padding-top: 3px;
          height: 53px;
        }
      }
    }
  }
  .apps-visual {
    margin-bottom: -59px;
    position: relative;
    .apps-visual-card {
      background: linear-gradient(180deg, rgba(255, 255, 255, 0.192) 0%, rgba(255, 255, 255, 0.088) 100%);
      border-radius: 20px 20px 0 0;
      padding: 20px;
      width: 285px;
      margin-top: -29px;
      margin-left: -10px;
      margin-bottom: -10px;
      position: relative;
      .apps-visual-card-header {
        margin-bottom: 36px;
        display: flex;
        position: relative;
        .apps-visual-card-header-avatar {
          margin-right: 10px;
          background-color: rgba(255, 255, 255, 0.5);
          width: 39px;
          height: 39px;
          border-radius: 10px;
          padding-top: 8px;
          img{
            display: block;
            margin: 0 auto;
            align-items: center;
            width: 22px;
            height: 26px;
          }
        }
        .apps-visual-card-header-description {
          margin-right: 83px;
          .hello {
            padding-top: 3px;
            font-size: 11px;
            line-height: 18px;
            color: $headings-text;
            font-weight: 600;
          }
          .member {
            font-size: 10px;
            color: $headings-text;
            font-weight: 500;
          }
        }
        .apps-visual-card-header-res {
          margin-top: 10px;
          img{
            height: 23px;
          }
        }
        .apps-visual-card-header-avatar1 {
          background-color: $highlighting-elements6;
          padding: 7px;
          border-radius: 50%;
          position: absolute;
          top: 76%;
          left: -41%;
          img {
            width: 45px;
          }
        }
      }
      .apps-visual-card-body {
        display: flex;
        background-color: $highlighting-elements5;
        padding: 20px;
        border-radius: 17px;
        margin-bottom: 150px;
        position: relative;
        .apps-visual-card-body-icon {
          width: 100px;
          img {
            margin-top: -6px;
            margin-left: 6px;
            width: 68px;
            height: 68px;
          }
        }
        .apps-visual-card-body-description {
          width: 106px;
          .header-text {
            color: $text-button;
            font-size: 11px;
            line-height: 18px;
            margin-bottom: 8px;
          }
          .descr-text {
            color: $text-color2;
            font-size: 8px;
            line-height: 12px;
            margin-bottom: 3px;
          }
        }
        .apps-visual-card-body-avatar2 {
          background-color: $highlighting-elements6;
          padding: 4px;
          border-radius: 50%;
          position: absolute;
          top: 65%;
          left: -29%;
          img {
            width: 38px;
            height: 38px;
          }
        }
        .apps-visual-card-body-avatar3 {
          background-color: $highlighting-elements6;
          padding: 5px;
          border-radius: 50%;
          position: absolute;
          top: 102%;
          right: -21%;
          img {
            width: 43px;
            height: 43px;
          }
        }
        .apps-visual-card-body-ref {
          position: absolute;
          top: 153%;
          left: -43%;
          display: flex;
          justify-content: space-between;
          width: 350px;
          .apps-visual-ref-course {
            padding: 20px 14px 20px 14px;
            background-color: $highlighting-elements6;
            border-radius: 17px;
            width: 159px;
            height: 94px;
            img {
              position: absolute;
              top: -30px;
              left: 30px;
              width: 100px;
              height: 88px;
            }
            p {
              margin-top: 40px;
              color: $text-button;
              font-weight: 600;
              font-size: 12px;
              i {
                border: solid $text-button;
                border-width: 0 2px 2px 0;
                display: inline-block;
                padding: 3px;
              }
              .right {
                transform: rotate(-45deg);
              }
            }
          }
          .apps-visual-ref-class {
            padding: 20px;
            background-color: $highlighting-elements6;
            border-radius: 17px;
            width: 159px;
            height: 94px;
            position: relative;
            img {
              position: absolute;
              top: -36px;
              left: 22px;
              width: 104px;
              height: 96px;
            }
            p {
              margin-top: 40px;
              color: $text-button;
              font-weight: 600;
              font-size: 12px;
              i {
                border: solid $text-button;
                border-width: 0 2px 2px 0;
                display: inline-block;
                padding: 3px;
              }
              .right {
                transform: rotate(-45deg);
              }
            }
          }
        }
      }
    }

  }
}
.apps::after {
  content: "";
  width: 100%;
  height: 100%;
  background: inherit;
  position: absolute;
  top: 0;
  left: 0;
  filter: blur(1.5rem);
  z-index: -1;
  transform:scale(1.15)
}

@keyframes hue {
  from{
    filter: hue-rotate(0);
  }
  to{
    filter: hue-rotate(360deg);
  }
}

@media screen and (max-width: 1360px){
  .apps .apps-info h3 {
    font-size: 47px;
    line-height: 75px;
    text-align: center;
  }
  .apps .apps-info p {
    font-size: 18px;
    line-height: 32px;
    text-align: center;
  }
  .apps {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    .apps-info {
      margin-bottom: 100px;
      h3 {
        margin: 0 auto 25px;
      }
      p {
        width: 300px;
        margin: 0 auto 65px;
      }
      .apps-info-brands {
        width: 400px;
        padding-left: 0;
        margin: 0 auto;
      }
    }
    .apps-visual {
      width: 100%;
      margin-bottom: -60px;
      .apps-visual-card {
        width: 300px;
        margin-left: 40%;
        margin-bottom: -10px;
        .apps-visual-card-header {
          .apps-visual-card-header-avatar1 {
            padding: 10px;
            top: 23%;
            left: -80%;
            img {
              width: 55px;
            }
          }
        }
        .apps-visual-card-body {
          padding: 30px;
          .apps-visual-card-body-icon {
            img {
            }
          }
          .apps-visual-card-body-description {
          }
          .apps-visual-card-body-avatar2 {
            padding: 6px;
            top: 65%;
            left: -51%;
            img {
              width: 42px;
              height: 42px;
            }
          }
          .apps-visual-card-body-avatar3 {
            padding: 7px;
            top: 91%;
            right: -60%;
            img {
              width: 48px;
              height: 48px;
            }
          }
          .apps-visual-card-body-ref {
            top: 137%;
            left: -37%;
            width: 417px;
          }
        }
      }

    }
  }
}

@media screen and (max-width: 990px){
  .apps-block-all {
    padding-top: 60px;
    padding-bottom: 54px;
  }
  .apps {
    .apps-info {
      .apps-info-brands {
        width: 380px;
      }
    }
    .apps-visual {
      width: 100%;
      .apps-visual-card {
        width: 300px;
        margin-left: 35%;
        .apps-visual-card-header {
          .apps-visual-card-header-avatar1 {
            padding: 7px;
            top: 10%;
            left: -51%;
            img {
              width: 48px;
            }
          }
        }
        .apps-visual-card-body {
          padding: 30px;
          .apps-visual-card-body-avatar2 {
            padding: 5px;
            top: 63%;
            left: -34%;
            img {
              width: 38px;
              height: 38px;
            }
          }
          .apps-visual-card-body-avatar3 {
            padding: 6px;
            top: 66%;
            right: -39%;
            img {
              width: 40px;
              height: 40px;
            }
          }
          .apps-visual-card-body-ref {
            top: 137%;
            left: -37%;
            width: 366px;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 768px){
  .apps .apps-info h3 {
    font-size: 22px;
    line-height: 50px;
  }
  .apps .apps-info p {
    font-size: 16px;
    line-height: 24px;
  }
  .apps {
    .apps-info {
      .apps-info-brands {
        max-width: 380px;
      }
    }
    .apps-visual {
      .apps-visual-card {
        width: 300px;
        margin-left: 30%;
        .apps-visual-card-header {
          .apps-visual-card-header-avatar1 {
            display: none;
            padding: 6px;
            top: 20%;
            left: -38%;
            img {
              width: 45px;
            }
          }
        }
        .apps-visual-card-body {
          padding: 30px;
          .apps-visual-card-body-avatar2 {
            padding: 4px;
            top: 71%;
            left: -30%;
            img {
              width: 35px;
              height: 35px;
            }
          }
          .apps-visual-card-body-avatar3 {
            padding: 5px;
            top: 76%;
            right: -24%;
            img {
              width: 38px;
              height: 38px;
            }
          }
          .apps-visual-card-body-ref {
            top: 137%;
            left: -21%;
            width: 342px;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 600px){
  .apps {
    .apps-info {
      .apps-info-brands {
        display: flex;
        flex-wrap: wrap;
        width: 290px;
        .apps-info-brands-google {
          margin: 0 auto;
          img {
            width: 100%;
            height: auto;
          }
        }
        .apps-info-brands-apple {
          margin: 0 auto;
          img {
            width: 100%;
            height: auto;
          }
        }
      }
    }
    .apps-visual {
      width: 300px;
      .apps-visual-card {
        width: 300px;
        margin-left: 11%;
        .apps-visual-card-header {
          .apps-visual-card-header-avatar1 {
            padding: 4px;
            top: 78%;
            left: -24%;
            img {
              width: 40px;
            }
          }
        }
        .apps-visual-card-body {
          padding: 30px;
          .apps-visual-card-body-avatar2 {
            padding: 4px;
            top: 89%;
            left: -21%;
          }
          .apps-visual-card-body-avatar3 {
            padding: 4px;
            top: 80%;
            right: -20%;
            img {
              width: 38px;
              height: 38px;
            }
          }
          .apps-visual-card-body-ref {
            top: 137%;
            left: -21%;
            width: 342px;
            .apps-visual-ref-course {
              width: 140px;
              height: 90px;
              img {
                top: -29px;
                left: 20px;
                width: 93px;
                height: 79px;
              }
            }
            .apps-visual-ref-class {
              width: 149px;
              height: 90px;
              img {
                top: -27px;
                left: 31px;
                width: 93px;
                height: 79px;
              }
            }
          }
        }
      }
    }
  }
}

@media screen and (max-width: 500px){
  .apps {
    .apps-info {
      transform: translateX(5%);
      p {
        width: 245px;
      }
    }
    .apps-visual {
      margin-bottom: 0;
      .apps-visual-card {
        border-radius: 20px;
        .apps-visual-card-header {
          .apps-visual-card-header-avatar1 {
            padding: 2px;
            top: 129%;
            left: -6%;
            z-index: 100;
            img {
              width: 40px;
            }
          }
        }
        .apps-visual-card-body {
          padding: 30px;
          .apps-visual-card-body-avatar2 {
            padding: 2px;
            top: 81%;
            left: -5%;
          }
          .apps-visual-card-body-avatar3 {
            padding: 2px;
            top: 73%;
            right: -7%;
            img {
              width: 38px;
              height: 38px;
            }
          }
          .apps-visual-card-body-ref {
            top: 146%;
            left: -4%;
            width: 280px;
            .apps-visual-ref-course {
              width: 130px;
              height: 90px;
              img {
                top: -27px;
                left: 16px;
                width: 92px;
                height: 86px;
              }
              p {
                font-size: 10px;
                i {
                  padding: 2px;
                }
              }
            }
            .apps-visual-ref-class {
              width: 130px;
              height: 90px;
              img {
                top: -24px;
                left: 21px;
                width: 92px;
                height: 86px;
              }
              p {
                font-size: 10px;
                i {
                  padding: 2px;
                }
              }
            }
          }
        }
      }
    }
  }
}

@media screen and (max-width: 320px){
  .apps {
    .apps-info {
      transform: translateX(5%);
    }
    .apps-visual {
      .apps-visual-card {
        border-radius: 20px;
        width: 270px;
        .apps-visual-card-header {
          .apps-visual-card-header-description {
            margin-right: 50px;
          }
          .apps-visual-card-header-avatar1 {
            padding: 2px;
            top: 129%;
            left: -6%;
            z-index: 100;
            img {
              width: 40px;
            }
          }
        }
        .apps-visual-card-body {
          padding: 30px;
          margin-bottom: 325px;
          .apps-visual-card-body-avatar2 {
            padding: 2px;
            top: 81%;
            left: -5%;
          }
          .apps-visual-card-body-avatar3 {
            padding: 2px;
            top: 73%;
            right: -7%;
            img {
              width: 38px;
              height: 38px;
            }
          }
          .apps-visual-card-body-ref {
            display: flex;
            flex-wrap: wrap;
            top: 146%;
            left: -13%;
            width: 290px;
            .apps-visual-ref-course {
              width: 150px;
              height: 90px;
              margin: 20px auto;
              img {
                top: -18px;
                left: 98px;
                width: 92px;
                height: 86px;
              }
              p {
                font-size: 10px;
                i {
                  padding: 2px;
                }
              }
            }
            .apps-visual-ref-class {
              width: 150px;
              height: 90px;
              margin: 20px auto;
              img {
                top: -17px;
                left: 32px;
                width: 92px;
                height: 86px;
              }
              p {
                font-size: 10px;
                i {
                  padding: 2px;
                }
              }
            }
          }
        }
      }
    }
  }
}

</style>