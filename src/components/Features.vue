<template>
  <div class="container">
    <!--features BLOCK-->
    <div class="features">
      <div class="features__block">
        <div class="features__img features__img_first"></div>
        <div class="features__text">
          <h3>Do you know how to level a cake?</h3>
          <p>
            After years of cake successes and flops, I’m confident in this homemade vanilla cake. During my recipe testing, I combined my white cake recipe and naked cake recipe. These are two reader favorites and I knew they’d be the best starting point.
          </p>
        </div>
      </div>

      <div class="features__block reverse">
        <div class="features__text p-l-0 p-r-70">
          <h3>Vanilla Cake Success Tips</h3>
          <p>
            I always eyeball the amount of frosting between cake layers, but I measured when I decorated the pictured cake. The vanilla buttercream recipe below yields about 6 cups of frosting. I recommend you use about 1.5 heaping cups of buttercream between each cake layer and reserve the last 3 cups for outside the cake.
          </p>
        </div>
        <div class="features__img features__img_second"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: "Features"
}
</script>

<style lang="scss">
.container{
  max-width: 1100px;
  margin: auto;
  padding: 0px 15px;
}
.p-l-0{
  padding-left: 0 !important;
}
.p-r-70{
  padding-right: 70px;
}
.features{
  &__block{
    display: flex;
    margin-bottom: 50px;
  }
  &__img{
    width: 59%;
    height: 350px;
    background-position: center;
    &_first{
      background-image: url("../assets/img.jpg");
    }
    &_second{
      background-image: url("../assets/img2.jpg");
    }
  }
  &__text{
    width: 41%;
    padding-top: 60px;
    padding-left: 70px;
  }
}

@media (max-width: 1025px) {
  .container{
    padding: 0px 30px;
  }
  .features{
    &__img{
      width: 50%;
    }
    &__text{
      width: 50%;
      padding-top: 35px;
      padding-left: 45px !important;
    }
    &__block{
      margin-bottom: 30px;
    }
  }
  .p-r-70{
    padding-right: 0px;
  }
  .reverse{
    flex-direction: row-reverse;
  }
}
@media(max-width: 767px){
  .container{
    padding: 0px 15px;
  }
  .features{
    &__block{
      margin-bottom: 40px;
      flex-direction: column;
    }
    &__img{
      width: 100%;
      height: 240px;
    }
    &__text{
      width: 100%;
      padding-top: 25px;
      padding-left: 0 !important;
    }
  }
  .reverse{
    flex-direction: column-reverse !important;
  }
}
</style>