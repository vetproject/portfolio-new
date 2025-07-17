<template>
  <div class="contact-box">
    <h1>Have a question? <span>Just ask!</span></h1>
    <p>Fill up the form, our team will get back to you within 24 Hours.</p>

    <form @submit.prevent="submitForm">
      <div class="ifo-con">
        <div class="input-box">
          <label for="name">Name</label>
          <input type="text" id="name" v-model="name" required />
        </div>
        <div class="input-box">
          <label for="email">Email</label>
          <input type="email" id="email" v-model="email" required />
        </div>
      </div>
      <div class="input-box">
        <label for="message">Message</label>
        <textarea id="message" v-model="message" required></textarea>
      </div>

      <!-- ✅ Moved inside form -->
      <button type="submit" class="submit-button">Submit Now</button>
    </form>

    <div class="contact-info">
      <div class="info-item">
        <i class="bi bi-telephone-fill"></i>
        <div class="info">
          <p>Phone Number</p>
          <p>+123 456 7890</p>
        </div>
      </div>
      <div class="info-item">
        <i class="bi bi-house-door-fill"></i>
        <div class="info">
          <p>Address:</p>
          <p>Phnom Penh, Cambodia</p>
        </div>
      </div>
      <div class="info-item">
        <i class="bi bi-envelope-fill"></i>
        <div class="info">
          <p>Email Address</p>
          <p>rin@gmail.com</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  data() {
    return {
      name: '',
      email: '',
      message: ''
    };
  },
  methods: {
    submitForm() {
      const params = {
        from_name: this.name,
        from_email: this.email,
        message: this.message
      };

      emailjs
        .send(
          'service_gyccpwi',     // ✅ Your EmailJS service ID
          'template_p1y4tge',    // ✅ Your EmailJS template ID
          params,
          'h9uza2R6KjyFCKDn-'    // ✅ Your EmailJS public key
        )
        .then(() => {
          alert('Message sent successfully!');
          this.name = '';
          this.email = '';
          this.message = '';
        })
        .catch((error) => {
          console.error('Failed to send email:', error);
          alert('Failed to send message.');
        });
    }
  }
};
</script>

<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap-icons/font/bootstrap-icons.css');

.contact-box {
  max-width: 800px;
  margin: 50px auto;
  padding: 40px;
  background-color: #ffffff;
  color: #000;
  border-radius: 12px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
  font-family: "Knewave", system-ui;
}

.contact-box h1 {
  font-size: 28px;
  margin-bottom: 10px;
  color: #ff5e62;
}

.contact-box h1 span {
  color: #000;
}

.contact-box p {
  margin-bottom: 30px;
}

form {
  margin-bottom: 30px;
}

.ifo-con {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.input-box {
  flex: 1 1 45%;
  display: flex;
  flex-direction: column;
  margin-bottom: 20px;
}

.input-box label {
  margin-bottom: 8px;
  font-size: 14px;
}

.input-box input,
.input-box textarea {
  padding: 12px;
  border: none;
  border-radius: 8px;
  background-color: #1a1b2f;
  color: #fff;
  font-size: 14px;
}

.input-box input:focus,
.input-box textarea:focus {
  outline: 2px solid #0d6efd;
}

.input-box textarea {
  resize: vertical;
  min-height: 100px;
}

.contact-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  border-radius: 10px;
}

.info-item {
  display: flex;
  align-items: center;
}

.info-item i {
  font-size: 24px;
  color: #6f42c1;
  margin-right: 10px;
}

.info-item .info {
  text-align: left;
}

.info-item p {
  margin: 0;
  color: #333;
}

.submit-button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  background-color: #6f42c1;
  color: white;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s;
  font-family: "Coiny", system-ui;
}

.submit-button:hover {
  background-color: #5a31a7;
}

@media (max-width: 768px) {
  .ifo-con {
    flex-direction: column;
  }

  .input-box {
    flex: 1 1 100%;
  }

  .contact-info {
    flex-direction: column;
    align-items: stretch;
  }

  .info-item {
    justify-content: center;
    margin-bottom: 15px;
  }

  .submit-button {
    margin-top: 10px;
  }
}
</style>
