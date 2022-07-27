<template>
  <div class="modal-vue">
    <!-- overlay -->
    <div class="overlay"></div>
    <!-- modal -->
    <div class="modal">
      <slot name="body">
        <button class="close" @click="$emit('close')">x</button>
      </slot>
      <div class="">
        <div class="">
          <div class="">
            <form id="feedback_form" @submit.prevent ='checkAndSend'>
              <div class="card">
                <div class="card-header">
                  <h3>Contact us</h3>
                </div>
                <div class="card-body">
                  <div v-if="answer.success"  role="alert">
                    <div>
                      {{ answer.text }}
                    </div>
                  </div>
                  <div v-if="answer.success === false" role="alert">
                    <div>
                      {{ answer.text }}
                    </div>
                  </div>
                  <div class="form">
                    <label for="fb_name" class="form-label">Your name</label>
                    <input type="text" class="form-control" :class="{'is-invalid': errors.name!==''}" id="fb_name" v-model.trim="name" @focus="resetError('name')">
                    <div class="form-text">{{ errors.name }}</div>
                  </div>
                  <div class="form">
                    <label for="fb_email" class="form-label">Email address</label>
                    <input type="text" class="form-control" :class="{'is-invalid': errors.email!==''}" id="fb_email" v-model.trim="email" @focus="resetError('email')">
                    <div class="form-text">{{ errors.email }}</div>
                  </div>
                  <div class="form">
                    <label for="fb_phone" class="form-label">Phone number</label>
                    <input type="number" class="form-control" :class="{'is-invalid': errors.phone!==''}" id="fb_phone" v-model.trim="phone" @focus="resetError('phone')">
                    <div class="form-text">{{ errors.phone }}</div>
                  </div>
                  <div class="form">
                    <label for="fb_subject" class="form-label">Subject</label>
                    <input type="text" class="form-control" :class="{'is-invalid': errors.subject!==''}" id="fb_subject" v-model.trim="subject" @focus="resetError('subject')">
                    <div class="form-text">{{ errors.subject }}</div>
                  </div>
                  <div class="form">
                    <label for="fb_message" class="form-label">Message</label>
                    <textarea class="form-control" :class="{'is-invalid': errors.message!==''}" id="fb_message" v-model.trim="message" @focus="resetError('massage')"></textarea>
                    <div class="form-text">{{ errors.message }}</div>
                  </div>
                </div>
                <div class="card-footer">
                  <button type="submit" class="btn">Send</button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'modal-block',
  el: '#app',
  data() {
    return {
      showModal: false,
      API_BOT_ID: '5336059209:AAE3iqce9jpn0WQTqpINcqvul0XgTHp0hxA',
      CHAT_ID: '-1001599421581',
      name: '',
      email: '',
      phone: '',
      subject: '',
      message: '',
      errors: {
        name: '',
        email: '',
        phone: '',
        subject: '',
        message: '',
      },
      answer: {
        success: null,
        text: '',
      }
    }
  },
  methods: {
    checkAndSend() {
      let valid = true
      if (this.name === '') {
        this.errors.name = 'Enter your name'
        valid = false
      }
      if (this.name.length === 1) {
        this.errors.name = 'Minimal name  length is two chars'
        valid = false
      }
      if (this.email === '') {
        this.errors.email = 'Enter your email address'
        valid = false
      } else {
        if (this.isValidEmail(this.email) === false) {
          this.errors.email = 'Enter valid email address'
          valid = false
        }
      }
      if (this.phone === '') {
        this.errors.phone = 'Enter phone number'
        valid = false
      }
      if (this.subject === '') {
        this.errors.subject = 'Enter subject text'
        valid = false
      }
      if (this.message === '') {
        this.errors.message = 'Enter message text'
        valid = false
      }
      if (valid) {
        const message_text = '<i>Feedback data</i>' +
            '%0a<b>Name: </b>' + this.name +
            '%0a<b>Email: </b>' + this.email +
            '%0a<b>Phone: </b>' + this.phone +
            '%0a<b>Subject: </b>' + this.subject +
            '%0a<b>Message: </b>' + this.message
        fetch(
            `https://api.telegram.org/bot${this.API_BOT_ID}/sendMessage?chat_id=${this.CHAT_ID}&text=${message_text}&parse_mode=HTML`).
            then(resp => {
              return resp.json()
            }).
            then(resp => {
              if (resp.ok) {
                this.answer.success = true
                this.answer.text = 'Message successfully send'
                this.name = this.email = this.phone = this.subject = this.message = ''
              } else {
                this.answer.success = false
                this.answer.text = resp.description
              }
              setTimeout(() => {
                this.answer.success = null
                this.answer.text = ''
              }, 3000)
            }).
            catch(() => {
              this.answer.success = false
              this.answer.text = 'AJAX error. Please try again later'
            })
      }
    },
    resetError(fld) {
      this.errors[fld] = ''
    },
    /* eslint-disable */
    isValidEmail(email) {
      return Boolean(email.match(
          /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      ));
      /* eslint-enable */
    }
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

.modal-vue .overlay {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
}
.modal-vue .modal {
  position: absolute;
  width: 300px;
  z-index: 9999;
  top: 80%;
  left: 50%;
  transform: translateX(-50%);
  margin: 0 auto;
  padding: 35px 10px;
  background-color: $focus-color;
  color: $border-color;
  border-radius: 20px;
}
.modal-vue .close{
  position: absolute;
  top: 15px;
  right: 20px;
  color: $highlighting-elements;
}
.card {
  position: relative;
  display: flex;
  flex-direction: column;
  min-width: 0;
  border-radius: 20px;
  padding: 5px;
  background: $background-color;
}
.card-body {
  flex: 1 1 auto;
  padding: 10px 10px;
}
.card-footer {
  padding: 5px;
  background-color: rgba(0, 0, 0, .03);
  margin: 0 auto;
}
h3 {
  color: $highlighting-elements;
  text-align: center;
  padding-top: 10px;
}
.form {
  margin-bottom: 8px;
}
.form-control {
  width: 100%;
  padding: 0.345rem 0.65rem;
  font-size: 1rem;
  color: #212529;
  background-color: $text-color2;
  border: 2px solid #ced4da;
  border-radius: 10px;
}
.form-text {
  color: $highlighting-elements;
  font-size: 12px;
  font-style: italic;
}
.form-label {
  color: $focus-color;
  font-size: 12px;
  font-style: italic;
}
.btn {
  cursor: pointer;
  display: inline-block;
  color: $headings-text3;
  text-align: center;
  text-decoration: none;
  vertical-align: middle;
  padding: 10px;
  font-size: 14px;
  border-radius: 20px;
  width: 100px;
  border: 1px solid $highlighting-elements;
  background-color: #1F2143;
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
.row>* {
  flex-shrink: 0;
  width: 100%;
  max-width: 100%;
}

@media screen and (max-width: 768px) {
  .modal-vue .modal {
    top: 10%;
    left: 50%;
  }
}
</style>
