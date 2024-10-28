<template>
  <div class="background-theme">
    <v-container fluid style="min-height: inherit; padding: 0%;">
      <!-- Title and Progress Bar -->
      <v-row no-gutters align="center" justify="center">
        <v-col cols="12" class="text-center mb-6">
          <span class="pageTitle">Our Services</span>
        </v-col>
        <v-col cols="12">
          <v-progress-linear color="black" rounded value="100" height="6"></v-progress-linear>
        </v-col>
      </v-row>

      <!-- Carousels for Service Cards -->
      <v-row style="place-content: center;">
        <v-col cols="3" >
          <v-carousel
            cycle
            hide-delimiters
            show-arrows-on-hover
            interval="1000"
            :show-arrows="false"
          >
            <v-carousel-item v-for="(service, index) in firstSetServices" :key="index">
              <ServiceCard :title="service.title" :icon="service.icon" :desc="service.desc" />
            </v-carousel-item>
          </v-carousel>
        </v-col>

        <v-col cols="3" style="padding-left: 120px;">
          <v-carousel
            cycle
            hide-delimiters
            show-arrows-on-hover
            interval="1000"
            :show-arrows="false"
          >
            <v-carousel-item v-for="(service, index) in secondSetServices" :key="index">
              <ServiceCard :title="service.title" :icon="service.icon" :desc="service.desc" />
            </v-carousel-item>
          </v-carousel>
        </v-col>
      </v-row>

      <!-- Spacer Row -->
      <v-row no-gutters class="footer" justify="center" align="center">
        <v-col cols="12" md="6" class="text-center">
          <v-btn
            text
            plain
            exact
            x-large
            color="black"
            style="font-size: x-large; font-weight: 600"
            @click="goToContactPage"
          >
            CLICK HERE TO CONTACT US
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import ServiceCard from '@/components/card/ServiceCard.vue';

export default {
  components: {
    ServiceCard
  },
  data() {
    return {
      firstSetServices: [
        {
          icon: "icon/post-guard.png",
          title: "Static Control Service",
          desc: "We ensure authorized access, protect data, manage visitors, and respond swiftly to security incidents."
        },
        {
          icon: "icon/cash-transit.png",
          title: "Cash - In-Transit (C.I.T)",
          desc: "We securely transport cash and valuables between locations using armored vehicles and trained personnel."
        },
        {
          icon: "icon/bodyguard.png",
          title: "Private Guards",
          desc: "We provide dedicated security personnel to protect individuals, properties, and assets with personalized attention."
        }
      ],
      secondSetServices: [
        {
          icon: "icon/gun.png",
          title: "Service arms control",
          desc: "We involve managing and securing firearms and weapons to prevent unauthorized access and ensure safety."
        },
        {
          icon: "icon/dog.png",
          title: "Dog Control Service",
          desc: "We involve the use of trained canines to enhance security measures, deter trespassers, and detect illicit substances."
        },
        {
          icon: "icon/analysis.png",
          title: "Consultants and safety training",
          desc: "We offer expert consultancy and training services to enhance security awareness and preparedness."
        },
        {
          icon: "icon/private-investigator.png",
          title: "Private Investigator",
          desc: "We provide investigation services to uncover information and gather evidence for various purposes."
        }
      ]
    };
  },
  methods: {
    goToContactPage() {
      // Replace this with your desired scroll functionality
      this.$vuetify.goTo('#contact-us');
    }
  }
};
</script>

<style scoped>
.background-theme {
  background-image: url('static/servicesbg.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 90vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 100px; /* Adjusted padding for better alignment */
}

.pageTitle {
  font-size: 5rem;
  font-weight: 700;
  color: #000000;
  margin-bottom: 20px;
}

.v-progress-linear {
  background-color: #000000;
  height: 6px;
  width: 100%;
  border-radius: 10px;
}

.footer {
  margin-top: 100px; /* Add some spacing to the footer */
  padding: 20px;
  background-color: rgba(248, 245, 245, 0.7);
  color: #ffffff;
}

.footer-title {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

@media (max-width: 600px) {
  .pageTitle {
    font-size: 2.5rem;
  }
}

@media (max-width: 960px) {
  .background-theme {
    padding-top: 50px; /* Adjust padding for smaller screens */
  }
}
</style>
