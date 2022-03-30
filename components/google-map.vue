<template>
  <div class="map-container"><div id="map"></div></div>
</template>
<script>
import { Loader } from '@googlemaps/js-api-loader'

export default {
  mounted() {
    const loader = new Loader({
      apiKey: process.env.NUXT_GOOGLE_MAPS_API_KEY,
      version: 'weekly',
    })
    let map
    loader.load().then(() => {
      // eslint-disable-next-line no-undef
      map = new google.maps.Map(document.getElementById('map'), {
        center: { lat: 59.334591, lng: 18.06324 },
        zoom: 12,
        styles: [
          {
            elementType: 'geometry',
            stylers: [
              {
                color: '#171b21',
              },
            ],
          },
          {
            elementType: 'labels.text.stroke',
            stylers: [
              {
                color: '#242f3e',
              },
            ],
          },
          {
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'administrative.locality',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'poi',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'poi.park',
            elementType: 'geometry',
            stylers: [
              {
                color: '#263c3f',
              },
            ],
          },
          {
            featureType: 'poi.park',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#ffffff',
              },
            ],
          },
          {
            featureType: 'road',
            elementType: 'geometry',
            stylers: [
              {
                color: '#38414e',
              },
            ],
          },
          {
            featureType: 'road', // calles
            elementType: 'geometry.stroke',
            stylers: [
              {
                color: '#212a37',
              },
            ],
          },
          {
            featureType: 'road',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#9ca5b3',
              },
            ],
          },
          {
            featureType: 'road.highway',
            elementType: 'geometry',
            stylers: [
              {
                color: '#746855', // calles
              },
            ],
          },
          {
            featureType: 'road.highway',
            elementType: 'geometry.stroke',
            stylers: [
              {
                color: '#171b21',
              },
            ],
          },
          {
            featureType: 'road.highway',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#f3d19c',
              },
            ],
          },
          {
            featureType: 'transit',
            elementType: 'geometry',
            stylers: [
              {
                color: '#2f3948', // transit
              },
            ],
          },
          {
            featureType: 'transit.station',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#d59563',
              },
            ],
          },
          {
            featureType: 'water',
            elementType: 'geometry',
            stylers: [
              {
                color: '#d0a77f', // agua
              },
            ],
          },
          {
            featureType: 'water',
            elementType: 'labels.text.fill',
            stylers: [
              {
                color: '#d0a77f',
              },
            ],
          },
          {
            featureType: 'water',
            elementType: 'labels.text.stroke',
            stylers: [
              {
                color: '#d0a77f',
              },
            ],
          },
        ],
      })
      // eslint-disable-next-line no-console
      console.log(map)
    })
  },
}
</script>

<style lang="scss">
.map-container {
  height: 50vh;
  padding: 2rem 0 0 0 !important;
  #map {
    height: 100%;
    border-radius: 5px;
  }
}

@media (min-width: 768px) {
  .map-container {
    height: 510px;
    padding-top: 5rem !important;
  }
}

@media (min-width: 960px) {
  .map-container {
    padding: 0 !important;
  }
}

@media (width: 653px) and (height: 280px) {
  .map-container {
    height: 90vh;
  }
}

@media (width: 640px) and (height: 360px) {
  .map-container {
    height: 90vh !important;
    padding: 0 !important;
  }
}
@media (width: 640px) and (height: 384px) {
  .map-container {
    height: 90vh !important;
    padding: 0 !important;
  }
}

@media (width: 768px) and (height: 1024px) {
  .map-container {
    margin-top: 4rem;
  }
}

@media (width: 1024px) and (height: 1366px) {
  .map-container {
    height: 40vh;
  }
}
</style>
