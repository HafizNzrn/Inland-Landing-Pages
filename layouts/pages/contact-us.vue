<template>
  <v-container fluid class="contact-us">
    <div style="padding: 100px 350px; min-height: 100vh ; align-content: center;">
      <v-row>
        <v-col cols="12" style="text-align: center">
          <div style="display: inline-block">
            <span class="pageTitle" style="display: inline ; font-size: xx-large;">Contact Us</span>
            <div style="display: block; padding: 0 25%">
              <v-progress-linear
                rounded
                value=100
                height=10
                color=white
              />
            </div>
          </div>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="12" md="5">
          <v-card
            elevation="5"
            style="padding: 30px"
            color="ghostwhite"
          >
            <v-card-title style="padding: 10px 0">
              Get in touch
            </v-card-title>
            <v-card-subtitle style="padding: 0">
              Fill in below form:
            </v-card-subtitle>
            <v-form @submit.prevent="submitForm">
              <v-text-field v-model="name" label="Name" required></v-text-field>
              <v-text-field v-model="phone" label="Phone Number" required></v-text-field>
              <v-text-field v-model="email" label="Email" required></v-text-field>
              <v-textarea v-model="message" label="Message" required></v-textarea>
              <v-btn color="primary" type="submit">Submit</v-btn>
            </v-form>
          </v-card>
        </v-col>
        <v-col cols="12" md="1" style="align-content: center; text-align: center;  padding-left: 100px;">
          <h2>OR</h2>
        </v-col>
        <v-col cols="12" md="5">
          <h2>Contact Information</h2>
          <p>Office Number : 03-61885524</p>
          <p>Email Address : officeisssb@gmail.com/insssb@yahoo.com</p>
          <h2>Location</h2>
          <p>NO. 17-2, BLOK B, JALAN MEDAN SELAYANG 1, MEDAN SELAYANG,68100 BATU CAVES, SELANGOR</p>
          <div style="display: block;">
            <Map></Map>
          </div>
        </v-col>
      </v-row>
    </div>
    </v-container>
  </template>
  
  <script>
  import Map from '@/components/card/map.vue';
  
  export default {
    components: {
      Map
    },
    data() {
      return {
        name: '',
        phone: '',
        email: '',
        message: ''
      };
    },
    methods: {
      submitForm() {
        // Here you can handle form submission, for example, send the data to your backend or display a confirmation message
        console.log('Form submitted');
        console.log('Name:', this.name);
        console.log('Phone Number:', this.phone);
        console.log('Email:', this.email);
        console.log('Message:', this.message);
      }
    }
  };
  </script>
  
  <style scoped>
  .contact-us{
  /* padding-top: 100px; */
  background-color: #f9f9f9;
  background-image: url('static/contact.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh; 
  }
  p {
    margin: 5px;
  }
  </style>
  