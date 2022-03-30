<template>
  <div class="social-media-contact">
    <a
      class="social-media-box"
      href="https://github.com/vsarrocchi"
      target="_blank"
    >
      <v-icon>mdi-github</v-icon>
    </a>
    <a
      class="social-media-box"
      href="https://linkedin.com/in/valesca-sarrocchi"
      target="_blank"
    >
      <v-icon>mdi-linkedin</v-icon>
    </a>
    <a class="social-media-box" href="mailto:valesca.sarrocchi.s@gmail.com">
      <v-icon>mdi-email</v-icon>
    </a>
  </div>
</template>

<style lang="scss" scoped>
.social-media-contact {
  display: none;
}

.social-media-contact i {
  color: #171b21;
}

a {
  text-decoration: none;
}

@media (min-width: 768px) {
  .social-media-contact {
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 111;
    margin: 15px;
    position: fixed;
    bottom: 0;
    right: 0;
  }

  .social-media-contact i {
    width: 50px;
    text-align: center;
    background-color: #d0a77f;
    border-radius: 30px;
    font-size: 1.5rem;
    padding: 0.8rem;
    margin: 0.5rem;
  }

  .social-media-box {
    position: relative;
    display: inline-block;
    transition: all 0.3s ease-in-out;
  }

  .social-media-box::after {
    content: '';
    position: absolute;
    z-index: -1;
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
  }

  .social-media-box:hover {
    transform: scale(1.2, 1.2);
  }

  .social-media-box:hover::after {
    opacity: 1;
  }
}
</style>
