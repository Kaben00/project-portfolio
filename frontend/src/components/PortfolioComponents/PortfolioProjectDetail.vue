<template>
  <v-container>
    <v-card-actions>
      <v-btn class="ma-2" color="primary" text @click="$emit('closeDetail')"><v-icon icon="mdi-arrow-left" start></v-icon>Back</v-btn>
    </v-card-actions>
    <div class="detailed-section">
      <div class="image-container">
        <v-img :src="detail.imageUrl" height="400px"></v-img>
      </div>
      <div class="text-content">
        <v-card-title>{{ detail.title }}</v-card-title>
        <v-card-text v-html="detail.description"></v-card-text>
        <v-card-text v-html="detail.techStack"></v-card-text>
        <div class="text-content-details">
          <div class="detailed-date-tasks" v-for="(detailEntry, index) in detail.details" :key="index">
          <h3>Date: {{ detailEntry.date }}</h3>
          <ul>
            <li v-for="(task, taskIndex) in detailEntry.tasks" :key="taskIndex" v-html="task">
            </li>
          </ul>
        </div>
        </div>
      </div>
    </div>
  </v-container>
</template>

<script>
    export default {
        data : () => ({
          
        }),

        props: {
          detail: Object,
        },

        mounted() {
        },

        computed: {
        },

        methods : {
        },
    }
</script>

<style scoped>
    .detailed-section {
      display: flex;
      align-items: flex-start;
    }

    .image-container {
      flex: 0 0 600px;
      margin-right: 30px;
    }

    .text-content {
      flex: 1;
      white-space: wrap;
      padding: 20px;
    }

    .text-content-details {
      scroll-behavior: smooth;
      overflow-y: auto;
    }

    .v-card {
        transition: box-shadow 0.3s ease-in-out;
        cursor: pointer;
        margin-bottom: 30px;
    }

    .v-card:hover {
        box-shadow: 5px 5px 15px rgba(0,0,0,0.3);
    }

    .detailed-date-tasks {
      margin-bottom: 16px;
    }

    .detailed-date-tasks h3 {
      font-weight: 500;
    }

    .v-card-title {
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