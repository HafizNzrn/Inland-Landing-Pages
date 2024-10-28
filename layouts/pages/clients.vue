<template>
  <v-container fluid class="our-client-container">
    <!-- Page Title -->
    <v-row justify="center">
      <v-col cols="12" class="text-center">
        <h1 class="page-title">Our Client</h1>
      </v-col>
    </v-row>

    <!-- Client Logos in a Single Card -->
    <v-row justify="center">
      <v-col cols="12" md="8">
        <v-card class="client-card" elevation="2">
          <v-row justify="center">
            <v-col cols="6" md="3" v-for="(client, index) in clients" :key="index" class="text-center">
              <v-img :src="client.logo" class="client-logo hover-img"></v-img>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      clients: [
        { logo: 'genius.jpeg' },
        { logo: 'grand.png' },
        { logo: 'kebajikan.png' },
        { logo: 'kolej.png' },
        { logo: 'kpm.png' },
        { logo: 'mardi2.png' },
        { logo: 'sunway2.png' },
      ]
    };
  }
};
</script>

<style scoped>
.our-client-container {
  padding-top: 100px;
  background-color: #f9f9f9;
  background-image: url('static/client.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 100vh;
}

.page-title {
  font-size: 3.5rem;
  font-weight: 700;
  color: #333;
  margin-bottom: 40px;
}

.client-card {
  padding: 20px;
}

.hover-img {
  transition: box-shadow 0.2s, transform 0.2s;
}

.hover-img:hover {
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  transform: translateY(-8px);
}

.client-logo {
  width: 100%;
  height: auto;
  padding: 10px;
}
</style>
