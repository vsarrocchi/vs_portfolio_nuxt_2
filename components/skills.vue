<template>
  <div>
    <h2 class="pb-12">Tekniska Kompetenser</h2>
    <div class="pb-12 d-flex justify-center flex-wrap">
      <div v-for="(item, i) in skills" :key="i" class="skills-box">
        <v-sheet
          v-if="item.type === 'first'"
          class="pa-5 ma-5 text-center"
          color="white"
          elevation="5"
        >
          <img
            :src="require(`../assets/images/svg/${item.url}`)"
            :alt="item.name"
          />
          <br />
          <span>{{ item.name }}</span>
        </v-sheet>
      </div>
    </div>
    <strong class="my-5">Jag har också blivit bekant med dessa tekniker</strong>
    <div class="pb-12">
      <div class="d-flex justify-center flex-wrap">
        <div v-for="(item, index) in skills" :key="index" class="skills-box">
          <v-sheet
            v-if="item.type === 'second'"
            class="pa-5 ma-5 text-center"
            color="white"
            elevation="5"
          >
            <img
              class="pa-0 ma-0"
              :src="require(`../assets/images/svg/${item.url}`)"
              :alt="item.name"
            />
            <br />
            <span>{{ item.name }}</span>
          </v-sheet>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    skills: [
      {
        type: 'first',
        url: 'javascript.svg',
        name: 'JavaScript',
      },
      {
        type: 'first',
        url: 'html5.svg',
        name: 'HTML5',
      },
      {
        type: 'first',
        url: 'css3.svg',
        name: 'CSS3',
      },
      {
        type: 'first',
        url: 'typescript.svg',
        name: 'TypeScript',
      },
      {
        type: 'first',
        url: 'nextjs.svg',
        name: 'Next.js',
      },
      {
        type: 'first',
        url: 'react.svg',
        name: 'React',
      },
      {
        type: 'first',
        url: 'sanity.svg',
        name: 'Sanity',
      },
      {
        type: 'first',
        url: 'contentful.svg',
        name: 'Contentful',
      },
      {
        type: 'first',
        url: 'sass.svg',
        name: 'Sass',
      },
      {
        type: 'first',
        url: 'tailwind.svg',
        name: 'Tailwind',
      },
      {
        type: 'first',
        url: 'git.svg',
        name: 'Git',
      },
      {
        type: 'first',
        url: 'github.svg',
        name: 'GitHub',
      },
      {
        type: 'first',
        url: 'responsive-design.svg',
        name: 'Responsive design',
      },
      {
        type: 'first',
        url: 'w3c.svg',
        name: 'Introduction to Web Accessibility',
      },
      {
        type: 'second',
        url: 'storybook.svg',
        name: 'Storybook',
      },
      {
        type: 'second',
        url: 'angular.svg',
        name: 'Angular',
      },
      {
        type: 'second',
        url: 'nuxt.svg',
        name: 'Nuxt',
      },
      {
        type: 'second',
        url: 'vue.svg',
        name: 'Vue',
      },
      {
        type: 'second',
        url: 'gimp.svg',
        name: 'Gimp',
      },
      {
        type: 'second',
        url: 'figma.svg',
        name: 'Figma',
      },
      {
        type: 'second',
        url: 'photoshop.svg',
        name: 'Adobe Photoshop',
      },
      {
        type: 'second',
        url: 'illustrator.svg',
        name: 'Adobe Illustrator',
      },
      {
        type: 'second',
        url: 'xd.svg',
        name: 'Adobe XD',
      },
      {
        type: 'second',
        url: 'gatsby.svg',
        name: 'Gatsby',
      },
      {
        type: 'second',
        url: 'vuetify.svg',
        name: 'Vuetify',
      },
      {
        type: 'second',
        url: 'bootstrap.svg',
        name: 'Bootstrap',
      },
      {
        type: 'second',
        url: 'wordpress.svg',
        name: 'Wordpress',
      },
      {
        type: 'second',
        url: 'php.svg',
        name: 'PHP',
      },
      {
        type: 'second',
        url: 'mysql.svg',
        name: 'MySQL',
      },
      {
        type: 'second',
        url: 'firebase.svg',
        name: 'Firebase',
      },
      {
        type: 'second',
        url: 'netlify.svg',
        name: 'Netlify',
      },
    ],
  }),
}
</script>
<style lang="scss">
.skills-box {
  display: flex;
  align-items: flex-end;
  height: 200px;
}

.skills-box img {
  height: 50px;
}
</style>
