<template>
  <v-row class="d-flex align-center justify-center social-content mx-0">
    <div class="d-flex flex-column pa-sm-16">
      <h2 class="text-center">Kontakt uppgifter</h2>
      <a href="mailto:valesca.sarrocchi.s@gmail.com"
        ><v-icon>mdi-email</v-icon>valesca.sarrocchi.s@gmail.com</a
      >
      <a href="https://github.com/vsarrocchi" target="_blank"
        ><v-icon>mdi-github</v-icon>https://github.com/vsarrocchi</a
      >
      <a href="https://linkedin.com/in/valesca-sarrocchi" target="_blank"
        ><v-icon>mdi-linkedin</v-icon
        >https://linkedin.com/in/valesca-sarrocchi</a
      >
    </div>
  </v-row>
</template>
<style lang="scss">
.social-content {
  background-color: #171b21;
  padding: 6rem 0 8rem 0;
  div {
    border: 2px solid #d0a77f;
    border-radius: 5px;
    color: #d0a77f !important;
    font-weight: bold;
    width: 90%;
    h2 {
      background-color: #171b21;
      width: 16rem;
      margin: auto;
      font-size: 2rem !important;
    }
    a {
      color: #d0a77f;
      display: flex;
      padding: 8px;
      text-decoration: none;
      .v-icon {
        color: #d0a77f;
        margin-right: 7px;
        font-size: 1.8rem;
      }
    }
  }
}

@media (min-width: 600px) and (max-width: 767px) {
  .social-content {
    padding: 1rem 0 8rem 0;
    div {
      width: unset;
    }
  }
}

@media (min-width: 768px) {
  .social-content {
    div {
      width: unset;
      h2 {
        transform: translateY(-90px);
      }
      a {
        transform: translateY(-20px);
        font-size: 1.2rem;
      }
    }
  }
}

@media (min-width: 960px) {
  .social-content {
    padding: 1rem 0 8rem 0;
  }
}

@media (width: 280px) and (height: 653px) {
  .social-content div {
    width: 100%;
  }
  .social-content div a {
    font-size: unset;
  }
}
</style>
