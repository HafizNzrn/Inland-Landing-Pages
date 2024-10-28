<template>
    <v-container class="customer-benefits-container">
      <!-- Title -->
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <h1 class="title">Customer Benefits</h1>
        </v-col>
      </v-row>
      
      <!-- Subtitle -->
      <v-row justify="center">
        <v-col cols="12" md="8" class="text-center">
          <p class="subtitle">
            Commercial security has always had its benefits over "in house" security. Inland Security seeks to enhance those benefits by providing quality services to its clients. Our superior benefits are unbeatable as they combine quality with cost savings.
          </p>
        </v-col>
      </v-row>
      
      <!-- Main Points -->
      <v-row justify="center">
        <v-col cols="12" md="10">
          <v-row>
            <v-col cols="12" md="6">
              <v-list two-line>
                <v-list-item v-for="(benefit, index) in firstColumnBenefits" :key="index" class="benefit-item">
                  <v-list-item-icon>
                    <v-icon>{{ benefit.icon }}</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>{{ benefit.title }}</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-col>
            <v-col cols="12" md="6">
              <v-list two-line>
                <v-list-item v-for="(benefit, index) in secondColumnBenefits" :key="index" class="benefit-item">
                  <v-list-item-icon>
                    <v-icon>{{ benefit.icon }}</v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title>{{ benefit.title }}</v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        firstColumnBenefits: [
          { icon: 'mdi-magnify', title: 'Security Survey & Recommendations.' },
          { icon: 'mdi-order-bool-ascending', title: 'Crystallizing Standing Order And Special Instructions.' },
          { icon: 'mdi-car', title: 'Supervision By Patrolling Officers.' },
          { icon: 'mdi-chart-line', title: 'Monthly Review Of Performance And Reports On Incidents And Security Weaknesses.' },
          { icon: 'mdi-shield-check', title: 'Adherence To Security Requirements Of Customers.' },
          { icon: 'mdi-account-group', title: 'Working In Co-operation With In-house Security Officers.' },
          { icon: 'mdi-alert-circle', title: 'Providing Feedback On Irregularities And Potential Losses And Risks.' }
        ],
        secondColumnBenefits: [
          { icon: 'mdi-account-off', title: 'Minimum Acquaintance With Employees Of Customers.' },
          { icon: 'mdi-shield-account', title: 'Full Insurance Coverage.' },
          { icon: 'mdi-cash-multiple', title: 'Substantial Saving In Costs And Can Be Tailored To Meet Individual Budgets.' },
          { icon: 'mdi-account-plus', title: 'Able To Increase Manpower On A Temporary Basis Or Short Notice.' },
          { icon: 'mdi-clock', title: '24 Hours 365 Days Contact Service.' },
          { icon: 'mdi-domain', title: 'Nationwide Branches To Service All Our Customers\' Installations.' }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  .customer-benefits-container {
    background-color: #f5f5f5;
    padding-top: 100px ; /* Added 100px padding-top */
    background-image: url('static/benefit2.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    min-height: 100vh;
    max-width: 1950px;
  }
  
  .title {
    font-size: 3.5rem !important; /* Increased the size of the title */
    font-weight: 700;
    color: #ffffff;
    margin-bottom: 20px;
    padding-top: 70px;
  }
  
  .subtitle {
    font-size: 1.2rem;
    font-weight: 400;
    color: #ffffff;
    margin-bottom: 40px;
  }
  
  .v-list-item-icon {
    margin-right: 10px;
  }
  
  .v-icon {
    font-size: 24px;
    color: #2196f3;
  }
  
  .v-list-item-title {
    font-size: 1rem;
    font-weight: 500;
    color: #333;
  }
  
  .benefit-item {
    transition: transform 0.2s, box-shadow 0.2s;
  }
  
  .benefit-item:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }
  </style>
  