<template>
  <v-container>
    <div v-if="!showDetail">
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
          <v-card @click="openDetail(item)">
            <v-img :src="item.imageUrl" height="200px"></v-img>
            <v-card-title>{{ item.title }}</v-card-title>
            <v-card-text>{{ item.description }}</v-card-text>
            <v-card-actions>
              <v-btn text :href="`#details-${item.id}`">Learn More</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </div>
    <div v-else>
      <portfolio-detail :detail="selectedItem" @closeDetail="closeDetail"/>
    </div>
  </v-container>
</template>

<script>
    import PortfolioDetail from './PortfolioDetail.vue';
    export default {
      components: {
        PortfolioDetail,
      },

        data : () => ({
            categories: ['All', 'WordPress', 'Vue', 'SiteSell'],
            selectedCategory: 'All',
            portfolioItems: [
        { 
          id: 1, 
          title: 'TaxPOD Website', 
          description: 'Revamp TaxPOD Website', 
          imageUrl: '/src/assets/images/taxpod-homepage-portfolio.webp', 
          category: 'WordPress' 
        },
        { 
          id: 2, 
          title: 'YYC & Co Website', 
          description: 'Revamp YYC & Co Website', 
          imageUrl: '/src/assets/images/yyc-co-homepage-portfolio.webp', 
          category: 'WordPress' 
        },
        { 
          id: 3, 
          title: 'YYC Advisors', 
          description: 'In Charge of YYC Advisors Project', 
          imageUrl: '/src/assets/images/yyc-advisors-homepage-portfolio.webp', 
          category: 'SiteSell' 
        },
        { 
          id: 2, 
          title: 'Portfolio Website', 
          description: 'Create a Website to Combine All Protfolio', 
          imageUrl: '/src/assets/images/taxpod-homepage-portfolio.webp', 
          category: 'Vue' 
        },
      ],
      showDetail: false,
      selectedItem: null,
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
          openDetail(item) {
            this.selectedItem = item;
            this.showDetail = true;
        },
          closeDetail() {
            this.showDetail = false;
            this.selectedItem = null;
        }
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