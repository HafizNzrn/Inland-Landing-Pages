<template>
    <v-container>
      <v-row justify="center">
        <v-col>
          <div ref="map" style="width: 500px; min-height: 300px;"></div>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    name: 'GoogleMap',
    data() {
      return {
        map: null,
        key: "AIzaSyA7PT6bTYFZ-rigMbnrGy7Lf6vmfXhKdeg",
        location: {
          lat: 3.2374115310215106, 
          lng: 101.70039792240584,
        },
        zoom: 16,
        markerTitle: 'We are here',
        markerPosition: {
          lat: 3.2374115310215106, 
          lng: 101.70039792240584,
        }
      };
    },
    mounted() {
      // Define the callback function in the global scope
      window.initMap = () => {
        this.initMap();
      };
      
      // Load Google Maps API script
      this.loadGoogleMaps();
    },
    methods: {
      loadGoogleMaps() {
        const script = document.createElement('script');
        script.src = `https://maps.googleapis.com/maps/api/js?key=${this.key}&callback=initMap`;
        script.async = true;
        script.defer = true;
        document.head.appendChild(script);
      },
      initMap() {
        this.map = new google.maps.Map(this.$refs.map, {
          center: this.location,
          zoom: this.zoom
        });
        this.addMarker();
      },
      addMarker() {
        const marker = new google.maps.Marker({
          position: this.markerPosition,
          map: this.map,
          title: this.markerTitle
        });
      }
    }
  };
  </script>
  