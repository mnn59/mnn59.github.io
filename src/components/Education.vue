<template>
  <section class="education-section" id="education">
    <v-container>
      <v-row>
        <v-col>
          <h1>Education</h1>
        </v-col>
      </v-row>
      <v-row>
        <v-col>
          <v-timeline reverse>
            <v-timeline-item
              v-for="(year, i) in years"
              :key="i"
              :color="year.color"
              small
            >
              <template v-slot:opposite>
                <span
                  :class="`headline font-weight-bold ${year.color}--text`"
                  v-text="year.year"
                ></span>
              </template>
              <div class="py-4">
                <h2
                  :class="`headline font-weight-light mb-4 ${year.color}--text`"
                >
                  {{ year.title }}
                </h2>
                <h3 class="mb-1">
                  {{ year.subTitle }}
                </h3>

                <!-- <g-image 
                src="~/helli.jpg"
                width="30"
                height="30"
                class="education-image" 
                /> -->

                <!-- <g-image :src="require(`${year.image}`)"/> -->

                <!-- <g-image 
                src="~/helli.jpg"
                width="30"
                height="30"
                class="education-image" 
                > -->

                <div>
                  {{ year.description }}
                </div>
                <v-btn tile color="success" :href="year.site" class="mt-5">
                  <v-icon left> mdi-arrow-right-box </v-icon>
                  Go to site
                </v-btn>
              </div>
            </v-timeline-item>
          </v-timeline>
        </v-col>
      </v-row>
      <br />
      <br />
    </v-container>
  </section>
</template>


<script>
export default {
  data() {
    return {
      years: [
        {
          color: "cyan",
          year: "1391-1395",
          title: "Allameh Helli High School",
          subTitle: "Mathematics and Physics",
          description:
            "I have studied at helli high school. Allameh Helli Schools, named after Al-Hilli, are schools found in various cities of Iran. Students study subjects in depth, similar to college courses. Allameh Helli Schools are for boys only, while ...",
          site: "https://helli.ir",
          image: "~/helli.jpg",
        },
        {
          color: "purple",
          year: "1396-1401",
          title: "Amirkabir University of Technology",
          subTitle: "Computer Engineering",
          description:
            "AUT was the second established technical university in Iran  and is referred to as the Mother of Engineering Universities.The university was founded in 1928 as a standard academy, and developed to the university of technology by Habib Nafisi in 1956, after ... ",
          site: "https://aut.ac.ir/en",
        },
      ],
    };
  },
  methods: {
    truncate(str) {
      if (str.length > 50) {
        return str.slice(0, 49) + "...";
      }
      return str;
    },
  },
};
</script>


<style scoped>
.education-section {
  background-color: #f4fffd;
}
.education-image {
  border-radius: 3px;
  border: 1px solid black;
}
</style>
