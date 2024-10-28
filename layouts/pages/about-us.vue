<template>
  <v-container fluid class="about-us-container">
    <!-- Page Title -->
    <v-row justify="center">
      <v-col cols="12" class="text-center">
        <h1 class="page-title">ABOUT US</h1>
      </v-col>
    </v-row>

    <!-- Tabs for Sections -->
    <v-tabs centered v-model="tab">
      <v-tab v-for="section in sections" :key="section.title">
        {{ section.title }}
      </v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab" style="width: 1880px;">
      <v-tab-item v-for="section in sections" :key="section.title">
        <v-container>
          <v-row justify="center">
            <v-col cols="12" md="8">
              <v-card class="pa-5">
                <v-card-title>{{ section.title }}</v-card-title>
                <v-card-text>{{ section.desc }}</v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-tab-item>
    </v-tabs-items>

    <!-- Carousel for Images or Highlights -->
    <v-row justify="center" class="mt-8">
      <v-col cols="12" md="8">
        <v-carousel cycle height="400" hide-delimiters>
          <v-carousel-item v-for="(image, i) in images" :key="i">
            <v-img :src="image.src" :alt="image.alt" />
          </v-carousel-item>
        </v-carousel>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      tab: null,
      sections: [
        {
          title: "OUR SELF",
          desc: `Inland Security Services Sdn. Bhd. (formerly Known as Segmen Ambang Sdn. Bhd.) was established on 21st Mac 2002 and was granted a license to provide security services from the Ministry of Home Affairs, Malaysia. Inland Security is also registered with the Ministry of Finance and is a member of the Malaysian Security Association (PIKM).
          In striving to become a developed nation, our Malaysian Government has been encouraging the setting up of factories and other companies. Thus, the need to safeguard the security of these establishments requires the support and services of quality security companies. We also realize the need to be competitively priced in this present market. It is only through being competitive together as 'business partners' that we can continue to serve our prime customers.
          As our industry is a service industry, which is labour intensive, we have reviewed the service level of our personnel. With that and our commitment to provide quality service, we have certified on the ISO 9001:2015 and ISO 18788:2015. At the same time, the need to have a higher level of security coverage due to increased risks, requires us to continuously improve our communication and surveillance system.
          Inland Security is blessed with a group of dynamic and experienced professional senior management and advisory personnel. Together, the team has been embarking on various projects to enhance our services and have established a goal, which is stipulated in our statement mission.The company has its headquarters in Batu Caves, Selangor and branches throughout East and West Malaysia and associate offices throughout the Asian region. We aim to provide a high level of service by ensuring that our personnel are fully trained and motivated. We carry out due diligence checks on all personnel and ensure that they are fully trained for the duties they are to perform.`
        },
        {
          title: "MISSION",
          desc: `We are in the business to protect & secure our customers' interest by being effective and timely through committed, skilful, disciplined & knowledgeable personnel`
        },
        {
          title: "VISION",
          desc: `We will add value for our customers by anticipating and identifying their needs and providing co-effective solutions. Through excellent and efficient service, we will meet our customers' expectations.`
        }
      ],
      images: [
        { src: 'image1.jpg', alt: 'Image 1' },
        { src: 'image2.jpg', alt: 'Image 2' },
        { src: 'image3.jpg', alt: 'Image 3' }
      ]
    };
  }
};
</script>
<style scoped>
.about-us-container {
  padding-top: 100px;
  background-image: url('static/modern.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
}

.page-title {
  font-size: 5.0rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 40px;
}

.v-tabs {
  margin-bottom: 20px;
  width: 1880px;
}

.v-tab {
  font-size: 1.2rem;
  font-weight: 500;
  
  
}

.v-card-title {
  font-size: 1.8rem;
  font-weight: 600;
}

.v-card-text {
  font-size: 1rem;
  font-weight: 400;
  line-height: 1.6;
  color: #666;
}

.v-carousel-item {
  transition: transform 0.2s;
}

.v-carousel-item:hover {
  transform: scale(1.05);
}
</style>
