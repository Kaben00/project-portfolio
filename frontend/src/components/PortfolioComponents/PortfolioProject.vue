<template>
  <v-container>
    <v-tabs v-model="selectedCategory" background-color="transparent" class="portolio-tab">
      <v-tab v-for="category in categories" :key="category" :value="category">
        {{ category }}
      </v-tab>
    </v-tabs>
    <v-row>
      <v-col
        cols="12"
        md="6"
        lg="4"
        v-for="item in filteredPortfolioItems"
        :key="item.id"
      >
        <v-card>
          <v-img :src="item.imageUrl" height="200px"></v-img>
          <v-card-title>{{ item.title }}</v-card-title>
          <v-card-text>{{ item.description }}</v-card-text>
          <v-card-actions>
            <v-btn text :href="`#details-${item.id}`">Learn More</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
    export default {
        data : () => ({
            categories: ['All', 'WordPress', 'Vue', 'SiteSell'],
            selectedCategory: 'All',
            portfolioItems: [
        { id: 1, title: 'TaxPOD Website', description: 'Revamp TaxPOD Website', imageUrl: '@/assets/images/taxpod-homepage-portfolio.webp', category: 'WordPress' },
        { id: 2, title: 'YYC & Co Website', description: 'Revamp YYC & Co Website', imageUrl: 'path/to/image2.jpg', category: 'WordPress' },
        { id: 3, title: 'YYC Advisors', description: 'In Charge of YYC Advisors Project', imageUrl: 'path/to/image2.jpg', category: 'SiteSell' },
        { id: 2, title: 'Kah Beng Portfolio Website', description: 'Create a Website to Combine All Protfolio', imageUrl: 'path/to/image2.jpg', category: 'Vue' },
      ],
        }),

        mounted() {
        },

        computed: {
            filteredPortfolioItems() {
                if (this.selectedCategory === 'All') {
                    return this.portfolioItems
                }
                return this.portfolioItems.filter(item => item.category === this.selectedCategory)
            }

        },

        methods : {
        },
    }
</script>

<style scoped>
    .v-card {
        transition: box-shadow 0.3s ease-in-out;
        cursor: pointer;
    }

    .v-card:hover {
        box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
    }

    .v-card-title {
        font-size: 18px;
        font-weight: bold;
    }

    .v-card-text {
        font-size: 14px;
        color: #666;
    }

    .v-btn {
        color: #1976D2;
    }

    .portolio-tab {
      margin-bottom: 30px;
    }
</style>