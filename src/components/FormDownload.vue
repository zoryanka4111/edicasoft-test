<template>
  <!--form BLOCK-->
  <form @submit.prevent="submit" class="form">
    <div class="form-group" :class="{ 'form-group--error': $v.name.$error }">
      <input class="form__input" placeholder="Your Name" v-model.trim="$v.name.$model"/>
    </div>
    <div v-if="$v.name.$dirty">
      <div class="error" v-if="!$v.name.required">Name is required</div>
      <div class="error" v-if="!$v.name.minLength">Name must have at least {{$v.name.$params.minLength.min}} letters.</div>
    </div>

    <div class="form-group" :class="{ 'form-group--error': $v.email.$error }">
      <input class="form__input" placeholder="Your Email" v-model.trim="$v.email.$model"/>
    </div>
    <div v-if="$v.email.$dirty">
      <div class="error" v-if="!$v.email.required">Name is required</div>
      <div class="error" v-if="!$v.email.email">Incorrect email</div>
    </div>

    <div class="form-group" :class="{ 'form-group--error': $v.phone.$error }">
      <input class="form__input" placeholder="Phone" v-model.trim="$v.phone.$model"/>
    </div>
    <div v-if="$v.phone.$dirty">
      <div class="error" v-if="!$v.phone.required">Phone is required</div>
      <div class="error" v-if="!$v.phone.phoneValid">Incorrect phone</div>
    </div>

    <button class="button" type="submit" :disabled="submitStatus === 'PENDING'">Download eBook Now</button>

    <span class="form__info">
        * We don’t share your personal info with anyone.
          Check out our Policy for more information.
      </span>
    <p class="form__info typo__p" v-if="submitStatus === 'OK'">Thanks for your submission!</p>
    <p class="form__info typo__p" v-if="submitStatus === 'ERROR'">Please fill the form correctly.</p>
    <p class="form__info typo__p" v-if="submitStatus === 'PENDING'">Sending...</p>
  </form>
</template>

<script>
import { required, minLength, email } from 'vuelidate/lib/validators'

const isPhone = (value) => /^\+?[0-9]+$/.test(value);

export default {
  name: "FormDownload",
  data() {
    return {
      name: '',
      email: '',
      phone: '',
      submitStatus: null
    }
  },
  validations: {
    name: {
      required,
      minLength: minLength(4)
    },
    email: {
      required,
      email
    },
    phone: {
      required,
      phoneValid : isPhone
    }
  },
  methods: {
    submit() {
      console.log('submit!')
      this.$v.$touch()
      if (this.$v.$invalid) {
        this.submitStatus = 'ERROR'
      } else {
        // do your submit logic here
        this.submitStatus = 'PENDING'
        setTimeout(() => {
          this.submitStatus = 'OK'
        }, 500)
      }
    }
  }
}
</script>

<style lang="scss">
  .form{
    max-width: 410px;
    position: absolute;
    padding: 75px 55px;
    background: #1C1C1C;
    opacity: 0.9;
    border-radius: 10px;
    &__info{
      color: #7A7A7A;
      font-size: 13px;
      font-weight: 300;
    }
    &__input{
      border: none;
      border-radius: 4px;
      font-size: 16px;
      height: 48px;
      line-height: 48px;
      padding: 2px 35px;
      width: 100%;
      &:focus{
        outline: none !important;
      }
    }
    &-group{
      margin-bottom: 20px;
    }
  }
  .error{
    color: #ffffff;
    font-size: 13px;
    margin-bottom: 10px;
  }
  .typo__p{
    margin-top: 10px;
    color: #ffffff;
  }
  .button{
    width: 100%;
    height: 51px;
    border: none;
    background: #0AD9C6;
    border-radius: 6px;
    font-size: 16px;
    font-weight: 700;
    transition: all ease 1s;
    margin-bottom: 15px;
    &:hover{
      opacity: 0.8;
      cursor: pointer;
    }
  }
  @media (max-width: 1300px) {
    .form{
      margin-left: 240px;
    }
  }
  @media (max-width: 1025px) {
    .form{
      margin-left: 0;
      right: 30px;
      max-width: 340px;
      padding: 40px 15px;;
    }
  }
  @media(max-width: 767px){
    .form{
      max-width: 100%;
      margin: 0px 15px;
      right: auto;
      bottom: 50px;
      padding: 40px 20px;
    }
  }
</style>