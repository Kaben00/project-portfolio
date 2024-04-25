<template>
  <v-container class="fill-height">
    <v-row justify="center">
      <v-col cols="12" md="8">
        <div class="about-us-description">
          <div class="section-h2-title">RESUME</div>
          <p class="text-body-1 section-description">A professional frontend developer.</p>
        </div>
          <div class="row">
            <div class="col-item-6">
              <h3 class="h3-title">Summary</h3>
              <div class="resume-item">
                <h4>Kah Beng</h4>
                <p>Self-motivated and disciplined front-end developer, seeking to utilize HTML5, CSS and JavaScript skills to
                deliver websites to the world. Have successfully debugged and published bug-free websites and
                webpages across multiples clients’ websites.
                </p>
              </div>
              <h3 class="h3-title">Education</h3>
              <div class="resume-item">
                <h4>E-Commerce</h4>
                <div class="company-year-of-service">
                  <div class="company-name">University Malaysia Sabah,&nbsp;</div>
                  <div class="year-of-service">2013-2017</div>
                  </div>
                  <p class="job-details">
                        Studied PHP, JavaScript, HTML, CSS in university
                  </p>
                </div>
            </div>
            <div class="col-item-6">
              <h3 class="h3-title">Professional Experience</h3>
              <v-expansion-panels v-model="panel">
                <v-expansion-panel
                  v-for="(workItem, index) in workExperienceItems" :key="index"
                >
                  <v-expansion-panel-title class="job-title"><h4>{{ workItem.jobName }}</h4></v-expansion-panel-title>
                  <v-expansion-panel-text>
                    <div class="job-item">
                      <div class="company-year-of-service">
                        <div class="company-name">{{ workItem.companyName }},&nbsp;</div>
                        <div class="year-of-service">{{ workItem.yearOfService }}</div>
                      </div>
                      <p 
                        v-for="task in workItem.jobDescription" 
                        :key="task"
                        class="job-details"
                      >
                        {{ task }}
                      </p>
                    </div>
                  </v-expansion-panel-text>
                </v-expansion-panel>
              </v-expansion-panels>
          </div>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    panel: [0],
    workExperienceItems: [{
      id: '1',
      jobName: 'WordPress Developer',
      companyName: 'YYC Advisors',
      yearOfService: '2023-Present',
      jobDescription: [
        'Designed and developed the company website, enhancing user experience and increasing visitor traffic by 20%.', 
        'Developed a custom WordPress plugin to automate content management, saving 10 hours of manual work per week.',
        'Customised WordPress themes using PHP and CSS, aligning with brand guidelines and improving site load time by 30%.',
        'Successfully published multiple websites to live servers, ensuring 99.9% uptime and resolving deployment issues.',
        'Implemented a test server on Digital Ocean, enabling streamlined pre-deployment testing and reducing bugs by 90%.',
        'Resolved critical server disk space issues by optimizing MySQL configurations and restarting services via command line, ensuring uninterrupted server operation.',
        'Optimized website images by adjusting size, resolution, and converting to WebP format, enhancing site speed and SEO.',
      ],
    },
    {
      id: '2',
      jobName: 'Knowledge Management Trainer',
      companyName: 'Accenture',
      yearOfService: '2019-2023',
      jobDescription: [
        'Task 1', 
        'Task 2'
      ],
    },
    {
      id: '3',
      jobName: 'Webmaster',
      companyName: '8verstudio',
      yearOfService: '2017-2017',
      jobDescription: [
        'Task 1', 
        'Task 2'
      ],
    },
  ]
  }),

  mounted() {
  },

  methods: {
  },
};
</script>

<style scoped>
  .about-us-description {
    color: black;
  }

  .v-expansion-panel {
    background-color: white;
    border-color: black;
    border-radius: 20px;
  }

  .v-expansion-panel-title, .v-expansion-panel-text {
    color: black;
  }

  .resume-item h4 {
    line-height: 18px;
    font-size: 18px;
    font-weight: 600;
    text-transform: uppercase;
    font-family: "Poppins", sans-serif;
    color: #0563bb;
    margin-bottom: 10px;
  }

  .resume-item {
    padding: 0 0 20px 20px;
    margin-top: -2px;
    border-left: 2px solid #0563bb;
    position: relative;
  }

  .resume-item::before {
    content: "";
    position: absolute;
    width: 16px;
    height: 16px;
    border-radius: 50px;
    left: -9px;
    top: 0;
    background: #fff;
    border: 2px solid #0563bb;
  }

  .resume-item p {
    color: black;
  }

  .job-title h4{
    line-height: 18px;
    font-size: 18px;
    font-weight: 600;
    text-transform: uppercase;
    font-family: "Poppins", sans-serif;
    color: #0563bb;
  }

  .job-item {
    padding: 0 0 20px 20px;
    margin-top: -2px;
    border-left: 2px solid #0563bb;
    position: relative;
  }

  .job-item::before {
    content: "";
    position: absolute;
    width: 16px;
    height: 16px;
    border-radius: 50px;
    left: -9px;
    top: 0;
    background: #fff;
    border: 2px solid #0563bb;
  }

  .company-year-of-service {
    font-weight: 500;
    background: #f7f8f9;
    padding: 5px 15px;
    display: inline-flex;
    margin-bottom: 10px;
    color: black;
  }

  .company-name {
    font-style: italic;
    background: #f7f8f9;
  }
</style>
