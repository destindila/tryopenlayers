<script setup>
import { ref } from 'vue'
import View from 'ol/View'
import Map from 'ol/Map'
import TileLayer from 'ol/layer/Tile'
import OSM from 'ol/source/OSM'
import 'ol/ol.css'
import VectorLayer from 'ol/layer/Vector'
import VectorSource from 'ol/source/Vector'
import GeoJSON from 'ol/format/GeoJSON'
import Point from 'ol/geom/Point';
import Polyline from 'ol/format/Polyline';
import Feature from 'ol/Feature';
import {Icon, Style} from 'ol/style';
import XYZ from 'ol/source/XYZ';
import {
  Circle as CircleStyle,
  Fill,
  Stroke,
} from 'ol/style';
import Overlay from 'ol/Overlay';
</script>

<template>
  <div ref="map-root" style="width: 100%; height: 100%">
    <div id="popup" class="ol-popup">
      <a href="#" id="popup-closer" class="ol-popup-closer"></a>
      <div id="popup-content"></div>
    </div>
  </div>
</template>

<script>
const data = {
    type: 'Feature',
    properties: {},
    geometry: {
      type: 'Polygon',
      coordinates: [
        [
          [
            112.00981210437732,
            -7.793959975032138
          ],
          [
            112.00865942417926,
            -7.801627833256745
          ],
          [
            112.00882409277966,
            -7.810845391609163
          ],
          [
            112.02339726384281,
            -7.8128846469590485
          ],
          [
            112.02504394983896,
            -7.812558366772151
          ],
          [
            112.03072501652326,
            -7.814516044068952
          ],
          [
            112.02701997303251,
            -7.823978021549323
          ],
          [
            112.03056034792445,
            -7.8257725103061375
          ],
          [
            112.03196003102067,
            -7.827077588186668
          ],
          [
            112.03130135662224,
            -7.83115593022147
          ],
          [
            112.0315483595221,
            -7.836131453434234
          ],
          [
            112.03006634212488,
            -7.84583763081217
          ],
          [
            112.00898876137848,
            -7.83711023788689
          ],
          [
            112.01030611017529,
            -7.827811692698333
          ],
          [
            112.00577772368734,
            -7.826996020938481
          ],
          [
            111.98511181443797,
            -7.828137960955303
          ],
          [
            111.99326291011891,
            -7.805380138181036
          ],
          [
            111.99770896230746,
            -7.802198838352098
          ],
          [
            112.00281368889443,
            -7.802851414649538
          ],
          [
            112.00207268019659,
            -7.800404248282902
          ],
          [
            112.00231968309487,
            -7.796733471887663
          ],
          [
            112.00166100869637,
            -7.795020431882307
          ],
          [
            112.00734207538244,
            -7.7928179415732615
          ],
          [
            112.00989443867672,
            -7.794041548730988
          ]
        ]
      ]
    }
  };
  
  export default {
    name: 'MapContainer',
    components: {},
    props: {},
    mounted() {
      const ft = new GeoJSON().readFeature(data, {
        featureProjection: 'EPSG:3857'
      });
      const iconStyle = new Style({
        image: new Icon({
          anchor: [0.5, 46],
          anchorXUnits: 'fraction',
          anchorYUnits: 'pixels',
          src: 'data/icon.png',
        }),
      });
      const lineStyle =  new Style({
        stroke: new Stroke({
          width: 6,
          color: 'blue',
        }),
      });
      
      ft.setStyle(lineStyle);
       const vectorLayer = new VectorLayer({
        source: new VectorSource({
          features: [ft],
        }),
      })
      const msjdAgung = new Feature({
        type: 'icon',
        geometry: new Point([12468923.804169679, -874033.7888506695]),
        name:'Masjid Agung Kediri',
        population: 4000,
        rainfall: 500,
      });
      const golden = new Feature({
        type: 'icon',
        geometry: new Point([12469924.511891412, -872696.2079720063]),
        name:'Golden Swalayan',
        population: 4000,
        rainfall: 500,
      });
      const wagu = new Feature({
        type: 'icon',
        geometry: new Point([12468067.403998489, -870719.4634317195]),
        name:'Wagu',  
        population: 4000,
        rainfall: 500,
      });
      
      const styleMarker =new Style({
        image: new Icon({
          anchor: [0.5, 1],
          src: 'data/icon.png',
          scale:[0.2,0.2]
        }),
      });
      
      msjdAgung.setStyle(styleMarker);
      wagu.setStyle(styleMarker);
      golden.setStyle(styleMarker);
      
      const vectorLayerMkr = new VectorLayer({
        source: new VectorSource({
          features: [msjdAgung, wagu, golden],
        }),
      })
      const map = new Map({
        target: this.$refs['map-root'],
        layers: [
          new TileLayer({
            source: new OSM(),
          }),
          vectorLayer,vectorLayerMkr
        ],
        view: new View({
          zoom:14,
          center: [12468974.756841773, -874008.9182193454],         
          constrainResolution: true
        }),
      })
      const element = document.getElementById('popup');
      const popup = new Overlay({
        element: element,
        positioning: 'bottom-center',
        stopEvent: false,
      });
      map.addOverlay(popup);
      let popover;
      function disposePopover() {
        if (popover) {
          popover.dispose();
          popover = undefined;
        }
      }
      map.on('click', function (evt) {
        const feature = map.forEachFeatureAtPixel(evt.pixel, function (feature) {
          return feature;
        });
        disposePopover();
        if (!feature) {
          return;
        }
        popup.setPosition(evt.coordinate);
        popover = new bootstrap.Popover(element, {
          placement: 'top',
          html: true,
          content: feature.get('name'),
        });
        popover.show();
      });
      //map.on('click', function(e){
      //  console.log(e.coordinate);
     // })
      map.on('pointermove', function (e) {
        const pixel = map.getEventPixel(e.originalEvent);
        const hit = map.hasFeatureAtPixel(pixel);
        map.getTarget().style.cursor = hit ? 'pointer' : '';
      });
      map.on('movestart', disposePopover);
      
    },
  }
  
</script>
<style scoped>
.read-the-docs {
  color: #888;
}
</style>