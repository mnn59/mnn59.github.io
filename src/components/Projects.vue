<template>
  <section 
  class="project-section"
  id="projects">
    <!-- <hr> -->
    <v-container>
      <v-row>
        <v-col>
          <h1>Projects</h1>
        </v-col>
      </v-row>
      <v-row class="justify-space-around mb-8 mt-4">
        <v-card
          v-for="project in projects"
          :key="project.name"
          class=""
          max-width="450"
          elevation="6"
        >
          <v-img
            class="white--text align-end"
            height="200px"
            :src="project.image"
          >
            <v-card-title>{{ project.name }}</v-card-title>
          </v-img>

          <v-card-subtitle class="pb-1"> {{ project.update }} </v-card-subtitle>

          <v-card-text class="text--primary">
            {{ truncate(project.description) }}
          </v-card-text>

          <v-card-actions>
            <v-btn color="#305F72" text :href="project.github">
              Github Repository
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-row>
      <!-- <br>
      <br> -->
    </v-container>
  </section>
</template>


<script>
export default {
  data() {
    return {
      projects: [
        {
          name: "Compiler project",
          github: "https://github.com/mnn59/compiler-project",
          description: "Lex and Yacc",
          update: "Updated on Nov 28, 2020",
          image: "https://picsum.photos/id/180/2400/1600.jpg/?blur",
        },
        // https://picsum.photos/id/233/500/300
        // https://images.unsplash.com/photo-1606851280869-8325b6268cd0?ixid=MXwxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwxfHx8ZW58MHx8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60
        {
          name: "Database project",
          github: "https://github.com/mnn59/DB-AUT",
          description: "MySQL",
          update: "Updated on Nov 24, 2020",
          image: "https://picsum.photos/id/2/5616/3744.jpg/?blur=10",
        },
      ],
    };
  },
  methods: {
    truncate(str) {
      if (str.length > 50){
        return str.slice(0,49) + '...'
      }
      return str;
    },
  },
};
</script>



<style scoped>
.project-section {
  /* #ffebcf */
  /* #ff9a00 */
  background-color: #ff9a00;
}
</style>