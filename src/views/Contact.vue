<template>
  <div id="contact">
    <h1>CONTACT US</h1>

    <p>If you have questions about your order or need any general information our customer service team will be happy to assist you.</p>

    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="fullName">FULL NAME*</label>
        <input v-validate="'required'" type="text" id="fullName" placeholder="e.g. robert smith" name="fullName" v-model="fullName">
        <span v-show="errors.has('fullName')" style="color: #fb4d01"> {{errors.first('fullName') }}</span>
      </div>

      <div class="form-group">
        <label for="email">EMAIL*</label>
        <input v-validate="'required|email'" type="email" id="email" placeholder="e.g.name@name.com" name="email" v-model="email">
        <span v-show="errors.has('email')" style="color: #fb4d01">{{ errors.first('email') }}</span>
      </div>

      <div class="form-group">
        <label for="company">COMPANY</label>
        <input type="text" id="company" placeholder="e.g. your company (optional)" name="company" v-model="company"> 
      </div>

      <div class="form-group">
        <label for="subject">SUBJECT *</label>
        <input v-validate="'required'" type="text" id="subject" placeholder="e.g. info" name="subject" v-model="subject">
        <span v-show="errors.has('subject')" style="color: #fb4d01">{{ errors.first('subject') }}</span> 
      </div>

      <div class="form-group">
        <label for="message">MESSAGE</label>
        <textarea id="message" style="height:150px" name="message"></textarea> 
      </div>

      <div class="form-group">
        <input type="submit" value="SEND">
      </div>

    </form>
  </div>
</template>

<script>
  export default {
    name: 'Contact',
    data: () => ({
      fullName: '',
      email: '',
      subject: ''
    }),
    methods: {
      handleSubmit () {
        this.$validator.validateAll().then((result) => {
          if (result) {
            alert('Validated! We will contact you within 48 hours')
            return
          }
          alert('Please fill in the required information.')
        })
      }
    }
  }
</script>