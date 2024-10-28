<template>
    <v-card class="overflow-hidden"
    width="100%"
    color="transparent"
    tile>
    <v-app-bar
            absolute
            color="transparent"
            dense  
            style="box-shadow: 0 0 0 0; place-self: center;"
            height="100"

        >
        <v-col cols="auto" style="width: 150px;">
        </v-col>
        <div v-for="(item, index) in firstSetItems" :key="index">
              <v-btn
                text
                plain
                exact
                x-large
                color="black"
                style="font-size: x-large; font-weight: 600"
                @click="handleClick(item)"
              >
                {{ item.title }}
              </v-btn>
            </div>
        <v-row align="center" style="place-content: center;">


        <v-col cols="auto">
            <v-img
            src="/logo/logo_inland.png"
            height="100px"
            style="max-width: 100px;"
            contain
            />   
        </v-col>
        <!-- <v-col cols="auto" class="logo-text">
            
            <v-img
            src="/font-header.png"
            height="1000px"
            style="max-width: 1000px;"
            contain
            />
            
        </v-col> -->
    </v-row>
    <div v-for="(item, index) in secondSetItems" :key="index">
              <v-btn
                text
                plain
                exact
                x-large
                color="black"
                style="font-size: x-large; font-weight: 600"
                @click="handleClick(item)"
              >
                {{ item.title }}
              </v-btn>
            </div>
            
        </v-app-bar>    
    </v-card>
</template>

<style scoped>
.logo-text{
    align-content: center;
}
/* .custom-font{
    font-family:Verdana, Geneva, Tahoma, sans-serif;
    font-size: 41px;
    font-weight: bolder;
    text-shadow: 2px 2px 4px rgba(173, 206, 203, 0.5);
} */
</style>
<script>
export default {
    data() {
        return {
            bg: 'transparent',
            textColor: 'black',
            items: [
                { title: 'Home', to: '#home' },
                { title: 'Services', to: '#services' },
                { title: 'About Us', to: '#about-us' },
                { title: 'Our Client', to: '#clients' },
                { title: 'Benefit', to: '#benefits' },
                { title: 'Contact Us', to: '#contact-us' },
            ],
            sectionOffsets: [], // Store the vertical offsets of each section
        };
    },
    computed: {
    firstSetItems() {
      return this.items.filter(item => item.title === 'Home' || item.title === 'Services' || item.title === 'Benefit');
    },
    secondSetItems() {
      return this.items.filter(item => item.title === 'About Us' || item.title === 'Our Client' || item.title === 'Contact Us' );
    },
  },

    mounted() {
        // Calculate the vertical offsets of each section
        this.calculateSectionOffsets();
        window.addEventListener('scroll', this.changeColor);
        this.changeColor(); // Call initially to set navbar color based on initial scroll position
    },

    destroyed() {
        window.removeEventListener('scroll', this.changeColor);
    },

    methods: {
        calculateSectionOffsets() {
            this.sectionOffsets = this.items.map(item => {
                const section = document.querySelector(item.to);
                return section.offsetTop;
            });
        },

        getCurrentSectionIndex() {
            const scrollPosition = document.documentElement.scrollTop || document.body.scrollTop;
            for (let i = this.sectionOffsets.length - 1; i >= 0; i--) {
                if (scrollPosition >= this.sectionOffsets[i]) {
                    return i;
                }
            }
            return 0; // Default to the first section
        },

        changeColor() {
            const currentSectionIndex = this.getCurrentSectionIndex();
            if (currentSectionIndex === 0) {
                this.bg = 'transparent';
                this.textColor = 'white';
            } else {
                this.bg = 'white';
                this.textColor = 'black'; // Change to your desired default text color
            }
        },
        handleClick(item) {
            if (item.title === 'Home') {
                window.scrollTo({
                    top: 0,
                    behavior: 'smooth'
                });
            } else {
                // For other buttons, you can implement your navigation logic
                // using $vuetify.goTo() or any other method you prefer
                // For demonstration, let's just scroll to the corresponding section
                const element = document.querySelector(item.to);
                if (element) {
                    element.scrollIntoView({ behavior: 'smooth' });
                }
            }
        }
        
    },
};
</script>

