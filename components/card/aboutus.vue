<template>
  <v-container>
  <v-card
    width="flex"
    min-height="fit-content"
    elevation="0"
    tile
    color="#f5f5f5"
  >
    <v-card-title
      style="margin-bottom: 30px;"
    >
      <v-row no-gutters justify="center" align="center">
        <v-col
          style="
            text-align: center;
            font-size: 30px; /* Adjust font size */
            word-break: keep-all;
            font-weight: 700; /* Adjust font weight */
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
            text-align: center;
            font-size: 16px; /* Adjust font size */
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
  </v-container>
</template>

<script>
export default {
  props: {
    title: {
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
.v-card-title {
  margin-bottom: 10px;
}
</style>
