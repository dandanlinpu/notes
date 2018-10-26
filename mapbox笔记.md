# 首次安装
在webpack打包环境中，npm install --save mapbox-gl
在index.html中,<link href='https://api.mapbox.com/mapbox-gl-js/v0.44.0/mapbox-gl.css' rel='stylesheet' />
地图要想100%全屏显示，要从App.vue:html, body{ margin:0; height:100%; },一层层往下设置height:100%,因为一个div的默认height为0
>一个最小实现的vue组件代码
```
<template>
    <div id="map"></div>
</template>

<script>
var mapboxgl = require("mapbox-gl/dist/mapbox-gl.js");

export default {
  name: "MapBoxTest",
  data() {
    return {
      msg: "map box test"
    };
  },
  mounted() {
    mapboxgl.accessToken = 'pk.eyJ1IjoiZGFuZGFubGlucHUiLCJhIjoiY2pkMDlwcTE5MHAzMzJxbzRwejh0NXU5aiJ9._LdgHHkMPETDZ1V_o0rJmw';
    var map = new mapboxgl.Map({
    container: 'map',
    style: 'mapbox://styles/mapbox/streets-v10'
    });
  }
};
</script>

<style scoped>
@import  'https://api.mapbox.com/mapbox-gl-js/v0.44.0/mapbox-gl.css';
#map {
    width:  500px;
    height: 500px;
}
</style>
```

# APi
queryRenderedFeatures()

vue的App.vue中默认text-align：center,会影响mapboxjs地图的显示。