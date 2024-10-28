<template>
    <div class="background-theme" style="min-height:100vh;">
    <v-row>
      <v-col
          no-gutters
        align="center"
        justify="center"
          style="min-height: 90vh; padding:0; align-content: center;"
      >
        <transition name="fade">
            <h1 v-if="showText" class="animated-text">INLAND </h1>
        </transition>
      </v-col>
      <v-col
        align="center"
        justify="center"
        style="align-content: center; max-width: 10px; padding: 0;">
        <div
          style="
            min-height :50%;
            max-height: 50%;
            width : 10px;
            background-color:black">
            </div>
      </v-col>
      <v-col
        no-gutters
        align="center"
        justify="center"
          style="min-height: 90vh; padding:0; align-content: center;"
      >
        <v-row style="justify-content: center; height: 100px;">
        <transition name="fade">
              <h1 v-if="showText" class="animated-text_1">SECURITY SERVICES </h1>
        </transition>
    </v-row>
        <v-row style="justify-content: center;">
      <transition name="fade">
        <h1 v-if="showText" class="animated-text_1" style="font-size: xx-large;">"YOUR SAFETY IS OUR MATTER"</h1>
      </transition>
    </v-row>
        </v-col>
        
    </v-row>
    
      
  </div>
</template>

  <script>
  export default {
    data() {
      return {
        showText: true,
      };
    },
  };
  </script>
  
  <style scoped>
  .background-theme {
    background-image: url('static/about-us.png');
    background-repeat: no-repeat;
    background-size: cover;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .animated-text {
    font-size: 10rem;
    color-scheme: #f3d7d7; /* Change text color as needed */
    text-align: center;
    opacity: 0;
    animation: fadeIn 4s ease forwards;
  }
  .animated-text_1 {
    font-size: 5rem;
    color: #f8f8fa; /* Change text color as needed */
    text-align: center;
    opacity: 0;
    animation: fadeIn 6s ease forwards;
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }
  </style>
  