<template>
  <form ref="form" @submit.prevent="sendEmail">
    <label>姓名</label>
    <input type="text" name="user_name">
    <label>邮箱</label>
    <input type="email" name="user_email">
    <label>公司</label>
    <input type="text" name="user_company">
    <label>你需要什么帮助</label>
    <textarea name="message"></textarea>
    <input type="submit" value="Send">
  </form>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  methods: {
    sendEmail() {
      emailjs.sendForm('service_j9efpor', 'template_ty92gji', this.$refs.form, 'mqDiUGzzur1Rhn2Sd')
        .then((result) => {
            console.log('SUCCESS!', result.text);
        }, (error) => {
            console.log('FAILED...', error.text);
        });
    }
  }
}
</script>