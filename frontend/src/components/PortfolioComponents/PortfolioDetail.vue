<template>
  <v-container>
    <v-card>
      <v-img :src="detail.imageUrl" height="400px"></v-img>
      <v-card-title>{{ detail.title }}</v-card-title>
      <v-card-text>{{ detail.description }}</v-card-text>
      <v-card-actions>
        <v-btn text @click="$emit('closeDetail')">Back</v-btn>
      </v-card-actions>
    </v-card>
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