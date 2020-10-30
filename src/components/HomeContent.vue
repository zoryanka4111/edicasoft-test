<template>
  <div>
    <!--hero BLOCK-->
    <div class="hero">
      <div class="hero__left">
        <div class="hero__text">
          <span>GET STARTED WITHIN 2 MINUTES</span>
          <h2>Learn How To Bake In 5 Easy Steps</h2>
          <p>
            No doubt, you need more one pot dinners in your life like this easy Bosnian-style chicken and rice. This recipe is made all over the world with countless variations on the theme.
          </p>
        </div>
      </div>
      <div class="hero__bg"></div>

      <!--form BLOCK-->
      <FormDownload/>
    </div>
  </div>
</template>

<script>

import FormDownload from "@/components/FormDownload";

export default {
  name: 'HomeContent',
  components: {
    FormDownload
  }
}
</script>

<style lang="scss">
  h1, h2, h3{
    font-weight: 700;
    margin: 0;
    margin-bottom: 30px;
    letter-spacing: -1.27px
  }
  h1{
    font-size: 40px;
  }
  h2{
    font-size: 30px;
  }
  h3{
    font-size: 22px;
  }
  p{
    font-size: 16px;
    font-weight: 400;
    color: #7A7A7A;
    margin: 0;
    line-height: 1.8;
  }
  .hero{
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 70px;
    position: relative;
    &__left{
      width: 50%;
      height: 770px;
      background: #E3F5F2;
      display: flex;
      align-items: center;
      span{
        font-size: 14px;
        font-weight: 700;
        color: #999999;
        text-transform: uppercase;
        letter-spacing: 1.08px;
        display: block;
        margin-bottom: 5px;
      }
    }
    &__text{
      max-width: 300px;
      margin: 20px 15px 0 75px;
    }
    &__bg{
      width: 50%;
      height: 770px;
      background: url("../assets/bg.jpg");
      background-size: cover;
      background-position: center;
    }
  }

  @media (max-width: 1025px) {
    h1, h2, h3{
      margin-bottom: 25px;
    }
    .hero{
      margin-bottom: 40px;
      &__left{
        width: 73%;
      }
      &__bg{
        width: 27%;
      }
      &__text{
        margin-left: 25px;
      }
    }
  }
  @media(max-width: 767px){
    h1{
      font-size: 30px;
    }
    h2{
      font-size: 26px;
    }
    h3{
      margin-bottom: 20px;
    }
    .hero{
      &__left{
        width: 85%;
        align-items: baseline;
        height: 800px;
        span{
          margin-bottom: 10px;
        }
      }
      &__bg{
        width: 15%;
        height: 800px;
      }
      &__text{
        margin: 50px 15px 0 17px;
      }
    }
  }
  @media(max-width: 374px){
    h2{
      margin-bottom: 15px;
    }
    p{
      font-size: 14px;
    }
    .hero{
      &__text{
        margin: 20px 15px 0 17px;
      }
    }
  }
</style>
