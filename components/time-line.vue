<template>
  <v-timeline>
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
          :class="`headline ${year.color}--text ${i % 2 !== 0 ? 'even' : ''}`"
          v-text="year.title"
        ></h2>
        <div
          :class="[
            i % 2 !== 0 ? 'even font-weight-light' : 'font-weight-light',
          ]"
          v-text="year.company"
        ></div>
      </div>
    </v-timeline-item>
  </v-timeline>
</template>

<script>
export default {
  data: () => ({
    years: [
      {
        color: '#d0a77f',
        year: 'Mars 2021 - Februari 2022',
        title: 'Junior Frontend utvecklare',
        company: 'Cinode',
      },
      {
        color: '#d0a77f',
        year: 'Juli 2020 - oktober 2020',
        title: 'Junior Frontend utvecklare',
        company: 'WCAG Networks',
      },
      {
        color: '#d0a77f',
        year: 'Mars 2018 - Maj 2020',
        title: 'Frontend utvecklare',
        company: 'Yrkesutbildning - Nackademin',
      },
      {
        color: '#d0a77f',
        year: 'Januari 2020 – Maj 2020',
        title: 'LIA 2 - Frontend utvecklare',
        company: 'B3 Consulting Group',
      },
      {
        color: '#d0a77f',
        year: 'September 2019 - December 2019',
        title: 'LIA 1 - Frontend utvecklare',
        company: 'EMG - Education Media Group',
      },
    ],
  }),
}
</script>
<style scoped>
.even {
  text-align: right;
}
</style>
