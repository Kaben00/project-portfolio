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
          <v-hover v-slot:default="{ hover }">
            <v-card
              class="d-flex flex-column"
              @click="openDetail(item)"
            >
              <v-img :src="item.imageUrl" height="200px">
              <v-fade-transition>
                <div
                  class="d-flex align-center justify-center fill-height info-overlay portfolio-background"
                  v-show="hover"
                >
                  <div class="hover-details">
                    <v-card-title>{{ item.title }}</v-card-title>
                    <v-card-text>{{ item.description }}</v-card-text>
                    <div class="view-more-icon">
                      <v-icon large color="black" :href="`#details-${item.id}`" class="d-flex align-center justify-center">mdi-magnify</v-icon>
                    </div>
                  </div>
                </div>
              </v-fade-transition>
            </v-img>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </div>
    <div v-else>
      <portfolio-detail :detail="selectedItem" @closeDetail="closeDetail"/>
    </div>
  </v-container>
</template>

<script>
    import PortfolioDetail from './PortfolioProjectDetail.vue';
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
          category: 'WordPress',
          details: [
            {
              date: '2023-06-01',            
              tasks: [
                'Installed WordPress on local machine.',
                'Test WordPress using GitHub for version control.',
              ],
            },
            {
              date: '2023-07-03',            
              tasks: [
                'Work on new design for the site.'
              ],
            },
            {
              date: '2023-07-10',            
              tasks: [
                'Discussion on design updates.'
              ],
            },
            {
              date: '2023-08-10',            
              tasks: [
                'Upload website to live server.'
              ],
            },
            {
              date: '2023-08-15',            
              tasks: [
                'Upload website to dev server to test plugins and customisation.'
              ],
            },
          ]
        },
        { 
          id: 2, 
          title: 'YYC & Co Website', 
          description: 'Revamp YYC & Co Website', 
          imageUrl: '/src/assets/images/yyc-co-homepage-portfolio.webp', 
          category: 'WordPress',
          details: [
            {
              date: '2023-11-17',            
              tasks: [
                'Installed WordPress on local machine.',
                'Research and prepare 2 proposals',
                'Meeting to determine design.'
              ],
            },
            {
              date: '2023-11-20',            
              tasks: [
                'Start development with information provided by PiC in local machine.',
              ],
            },
            {
              date: '2023-11-23',            
              tasks: [
                'Setup server in Digital Ocean for development and quick review by PiC.',
              ],
            },
            {
              date: '2024-01-23',            
              tasks: [
                'Deploy website to live server.',
              ],
            },
            {
              date: '2024-02-23',            
              tasks: [
                'Discussion for development of page for Singapore.',
                'Start development.'
              ],
            },
            {
              date: '2024-03-04',            
              tasks: [
                'Deploy page to live server.',
              ],
            },
            {
              date: '2024-04-08',            
              tasks: [
                'Work on Singapore version page to show up in Google Search when use keyword "YYC Singapore".',
                'Research on Google Search Console not fetching XML correctly.',
              ],
            },
          ]
        },
        { 
          id: 3, 
          title: '<a href="https://www.yycadvisors.com/" target="_blank">YYC Advisors</a>', 
          description: 'In Charge of YYC Advisors Project', 
          imageUrl: '/src/assets/images/yyc-advisors-homepage-portfolio.webp', 
          category: 'SiteSell',
          details: [
            {
              date: '2023-06-01',            
              tasks: [
                'Utilized SiteSell for CMS capabilities.',
                'Update slider with Js.',
                'Updated page with new design and information.'
              ],
            },
            {
              date: '2024-04-24',            
              tasks: [
                'Redesigned Articles page, <a href="https://www.yycadvisors.com/accounting-new-design.html" target="_blank">link</a>',
              ],
            },
            {
              date: '2024-04-26',            
              tasks: [
                'Provides Generative Artificial Intelligent (GAI) Prompt Training',
                'Integrated Google Tag Manager and Google Search Console Code Snippets into the website' 
              ],
            },
          ]
        },
        { 
          id: 4, 
          title: 'Portfolio Website', 
          description: 'Create a Website to Combine All Protfolio', 
          imageUrl: '/src/assets/images/portfolio-page.webp', 
          category: 'Vue',
          details: [
            {
              date: '2024-03-25',            
              tasks: [
                'Setup locally.',
                'Search for design online.',
                'Start development.'
              ],
            },
            {
              date: '2024-04-03',            
              tasks: [
                'Develop Portfolio section.',
                'Discussion on file path',
              ],
            },
            {
              date: '2024-04-17',            
              tasks: [
                'Futhur Enhance Portfolio section.',
                'Fill in the tasks and date.',
              ],
            },
          ]
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
        transition: box-shadow 0.5s ease-in-out;
        cursor: pointer;
    }

    .v-card:hover {
        box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
        background: rgba(146, 69, 69, 0.5)
    }

    .portfolio-background:hover {
      background: rgba(255, 255, 255, 0.8);
    }

    .info-overlay .hover-details {
      transition: transform 0.5s ease-out, opacity 0.5s ease;
      transform: scale(0);
      opacity: 0;
    }

    .info-overlay:hover .hover-details {
      display: block;
      color: black;
      text-align: center;
      transform: scale(1); /* Scale up to normal size */
      opacity: 1; /* Fade in */

    }

    .info-overlay:hover .hover-details .v-card-title,
    .info-overlay:hover .hover-details .v-card-text,
    .info-overlay:hover .hover-details .v-icon,
    .info-overlay:hover .hover-details .v-btn {
        display: flex; /* show text on hover */
        color: black;
        text-align: center;
        justify-content: center;
        align-items: center;
    }

    .view-more-icon {
      display: flex;
      justify-content: center;
      align-items: center;
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