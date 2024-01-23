<script setup>
import 'mapbox-gl/dist/mapbox-gl.css'
import mapboxgl from 'mapbox-gl'

mapboxgl.accessToken = 'pk.eyJ1Ijoic3VuZ3VvcWkiLCJhIjoiY2xqcXlvajd0MGMxNzNtbWpoZHliaWVtYyJ9.N3bTvCedxVfugnrCSRT2kw'

const map = new mapboxgl.Map({
  container: 'map', // container ID
  style: 'mapbox://styles/mapbox/streets-v12', // style URL
  center: [-74.5, 40], // starting position [lng, lat]
  zoom: 9, // starting zoom
})

// 全屏
map.addControl(new mapboxgl.FullscreenControl())

// 比例尺
map.addControl(new mapboxgl.ScaleControl())

// 缩放
map.addControl(new mapboxgl.NavigationControl({ visualizePitch: true }))

// 定位
map.addControl(new mapboxgl.GeolocateControl({
  positionOptions: {
    enableHighAccuracy: true,
  },
  trackUserLocation: true,
  showUserHeading: true,
}))
</script>

<template>
  <div id="map" />
</template>

<style lang="scss" scoped>

</style>
