<template>

  <div class="container">
      <div class="carousel">
          <input type="radio" id="carousel-1" name="carousel[]" checked>
          <input type="radio" id="carousel-2" name="carousel[]">
      <input type="radio" id="carousel-3" name="carousel[]">
          <input type="radio" id="carousel-4" name="carousel[]">
          <input type="radio" id="carousel-5" name="carousel[]">
          <ul class="carousel__items">
              <li class="carousel__item"><img src="~/assets/img/beautify.jpg" alt=""></li>
              <li class="carousel__item"><img src="~/assets/img/beataudio.jpg" alt=""></li>
              <li class="carousel__item"><img src="~/assets/img/fish.jpg" alt=""></li>
              <li class="carousel__item"><img src="~/assets/img/lamborghini.jpg" alt=""></li>
              <li class="carousel__item"><img src="~/assets/img/rainbow.jpg" alt=""></li>
          </ul>
      <div class="carousel__prev">
          <label for="carousel-1"></label>
          <label for="carousel-2"></label>
          <label for="carousel-3"></label>
          <label for="carousel-4"></label>
          <label for="carousel-5"></label>
      </div>
      <div class="carousel__next">
        <label for="carousel-1"></label>
        <label for="carousel-2"></label>
        <label for="carousel-3"></label>
        <label for="carousel-4"></label>
        <label for="carousel-5"></label>
      </div>
      <div class="carousel__nav">
        <label for="carousel-1"></label>
        <label for="carousel-2"></label>
        <label for="carousel-3"></label>
        <label for="carousel-4"></label>
        <label for="carousel-5"></label>
      </div>
    </div>
    <br><br>
    <hr class="lin">
   <div class="container mb-5">
      <div class="row">
        <div class="col-sm-4">
          <h3 class="headings">Achievements</h3>
          <hr class="lin">
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
          <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris...</p>
        </div>
        <div class="col-sm-4">
          <h3 class="headings">Committees</h3>
            <hr class="lin">
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
          <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris...</p>
        </div>
        <div class="col-sm-4">
          <h3 class="headings">News</h3>
            <hr class="lin">        
          <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>
          <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris...</p>
        </div>
      </div>
    </div>
    <div class="container mt-5">
      <h1 class="headings text-center h1">Get in Touch</h1>
      <hr class="line">
      <div class="row">
        <div class="col-md-3">
           <a href="#"><img class="img1" src="~/assets/img/facebook.svg" alt=""></a>
        </div>
        <div class="col-md-3">
            <a href="#"><img  class="img1" src="~/assets/img/twitter.svg" alt=""></a>
        </div>
        <div class="col-md-3">
          <a href="#"><img  class="img1" src="~/assets/img/instagram.svg" alt=""></a>
        </div>
        <div class="col-md-3">
          <a href="#"><img  class="img1" src="~/assets/img/phone-call.svg" alt=""></a>
        </div>
      </div>
    </div>
  </div>

</template>

<script>

  export default {
    components: {
     
  }
}
</script>

<style lang="scss" scoped>

.img1{
  width: 300px;
  height: 60px;
  margin-top: 40px;
  margin-bottom: 50px;
}
/**
 * Carousel.sass
 * @author: Dang Van Thanh
 * @github: https://github.com/dangvanthanh/carousel.sass
 * @description: A Simple Carousel Pure CSS Using Sass
 * @version: 1.0.0
 */
%animation-default {
  opacity: 1 !important;
  z-index: 1;
}

@mixin carousel($items, $animation: 'default') {
  .carousel {
    width: 100%;
    position: relative;
    overflow: hidden;

    > input[type="radio"] {
      position: absolute;
      left: 0;
      opacity: 0;
      top: 0;

      &:checked {
        ~ .carousel__items .carousel__item,
        ~ .carousel__prev > label,
        ~ .carousel__next > label {
          opacity: 0;
        }
      }

      @for $i from 1 through $items {
        &:nth-child(#{$i}) {
          &:checked {
            ~ .carousel__items .carousel__item {
              @if $animation == 'default' {
                &:nth-child(#{$i}) {
                  opacity: 1;
                }
              }
            }

            ~ .carousel__prev {
              > label {
                @if $i == 1 {
                  &:nth-child(#{$items}) {
                    @extend %animation-default;
                  }
                } @else if $i == $items {
                  &:nth-child(#{$items - 1}) {
                    @extend %animation-default;
                  }
                } @else {
                  &:nth-child(#{$i - 1}) {
                    @extend %animation-default;
                  }
                }
              }
            }

            ~ .carousel__next {
              > label {
                @if $i == $items {
                  &:nth-child(1) {
                    @extend %animation-default;
                  }
                } @else {
                  &:nth-child(#{$i + 1}) {width: 40%;
  height: 40%;
    }.child {
  width: 40%;
  height: 40%;
                    @extend %animation-default;
                  }
                }
              }
            }

            ~ .carousel__nav {
              > label {
                &:nth-child(#{$i}) {
                  background: #ccc;
                  cursor: default;
                  pointer-events: none;
                }
              }
            }
          }
        }
      }
    }

    &__items {
      margin: 0;
      padding: 0;
      list-style-type: none;
      width: 100%;
      height: 500px;
      position: relative;
    }

    &__item {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
      transition: opacity 2s;
      -webkit-transition: opacity 2s;

      img {
        width: 100%;
        vertical-align: middle;
      }
    }

    &__prev,
    &__next {
      > label {
        border: 1px solid #fff;
        border-radius: 50%;
        cursor: pointer;
        display: block;
        width: 40px;
        height: 40px;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        -webkit-transform: translateY(-50%);
        transition: all .3s ease;
        -webkit-transition: all .3s ease;
        opacity: 0;
        z-index: 2;
        &:hover,
        &:focus {
          opacity: .5 !important;
        }

        &:before,
        &:after {
          content: "";
          position: absolute;
          width: inherit;
          height: inherit;
        }

        &:before {
          background: linear-gradient(to top, #fff 0%, #fff 10%, rgba(51, 51, 51, 0) 10%),
                      linear-gradient(to left, #fff 0%, #fff 10%, rgba(51, 51, 51, 0) 10%);
          width: 60%;
          height: 60%;
          top: 20%;
        }
      }
    }

    &__prev {
      > label {
        left: 2%;

        &:before {
          left: 35%;
          top: 20%;
          transform: rotate(135deg);
          -webkit-transform: rotate(135deg);
        }
      }
    }

    &__next {
      > label {
        right: 2%;

        &:before {
          left: 10%;
          transform: rotate(315deg);
          -webkit-transform: rotate(315deg);
        }
      }
    }

    &__nav {
      position: absolute;
      bottom: 3%;
      left: 0;
      text-align: center;
      width: 100%;
      z-index: 3;

      > label {
        border: 1px solid #fff;
        display: inline-block;
        border-radius: 50%;
        cursor: pointer;
        margin: 0 .125%;
        width: 20px;
        height: 20px;
      }
    }
  }
}

*,
*:before,
*:after {
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
}

body {
  background: #fcfcfc;
  margin: 0;
}

.container {
  width: 90%;
  min-width: 800px;
  margin: 0px auto;
}

@include carousel(5);

// flex goes here
.line{
  border: solid 2px #677;
  width: 50%;
  margin-left: 250px;

  
}
.lin{
  border: solid 2px #677;
  
}

</style>

