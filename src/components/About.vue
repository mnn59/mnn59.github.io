<template>
  <section 
  class="about-section"
  id="about">
    <v-container>
      <v-row>
        <v-col sm="4">
          <g-image
            alt="Profile image"
            src="~/mahdi3.jpg"
            width="300"
            class="profile-image mt-1"
          />
        </v-col>
        <v-col sm="3" class="d-flex flex-column justify-center">
          <h1 >Hi, I'm mahdi. 😊</h1>
          
          <p>
            I'm Computer Engineer student and Front-end Developer.<br>
            My Favourite emojies are : <br>
            <pre>   I ❤️ coding.<br></pre>
            <pre>   My 💻 is old.<br></pre>
            <pre>   My hobby is following <a href="https://www.jadi.net" style="text-decoration: none">@jadi.</a></pre>
          </p>
          
          <div>
            <v-btn tile color="success" href="https:/github.com/mnn59/">
              <v-icon left> mdi-github </v-icon>
              Github
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>



<style scoped>
.about-section {
  background-color: #f4fffd;
}

.profile-image {
  border-radius: 7px;
}
</style>
