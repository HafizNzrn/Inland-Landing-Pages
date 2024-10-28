<template>
      <v-card
        width="350"
        height="400"
        elevation="0"
        tile
        color="#f5f5f5"
      >
        <v-card-title
          style="margin-bottom: 10px;"
        >
          <v-row no-gutters>
            <v-col cols="12">
              <v-img :src="icon" height="200" width="300" contain />
        </v-col>
          </v-row>
          <v-row no-gutters justify="center" align="center">
            <v-col
              style="
                text-align: center;
                font-size: x-large;
                word-break: keep-all;
                font-weight: 600;
              "
              cols="12"
            >
              {{ title }}
        </v-col>
      </v-row>
    </v-card-title>
    <v-card-subtitle>
          <v-row no-gutters>
            <v-col
              style="
                text-align: justify;
                font-size: large;
                word-break: keep-all;
                color: grey;
                font-weight: 300;
              "
              cols="12"
            >
          {{ desc }}
        </v-col>
      </v-row>
    </v-card-subtitle>
  </v-card>
</template>
  
  <style>

  </style>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    icon: {
      type: String,
      required: true,
    },
    desc: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.card-title {
  font-size: 1.5rem;
  font-weight: 600;
  word-break: keep-all;
  color: #000000;
  background-color: #ffffff;
  padding: 10px;
  border-radius: 5px;
}

.card-desc {
  text-align: justify;
  font-size: 1rem;
  color: grey;
  font-weight: 300;
  padding: 10px;
  border-radius: 5px;
  background-color: #ffffff;
}

.text-center {
  text-align: center;
}

.mb-4 {
  margin-bottom: 20px;
}

.img-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 200px;
}

.icon-img {
  max-height: 100%;
  max-width: 100%;
}
</style>
