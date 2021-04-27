<template>
  <a-scene v-pre>
    <a-plane v-pre rotation="-90 0 0" width="30" height="30"></a-plane>

    <a-light v-pre type="ambient" color="#445451"></a-light>
    <a-light v-pre type="point" intensity="2" position="0 3 -3" color="#445451"></a-light>

    <a-camera v-pre
        look-controls
        wasd-controls="acceleration:100"
        position="0 1 4"
        cursor-visible="true"
        cursor-scale="2"
        cursor-color="#0095DD"
        cursor-opacity="0.5">
    </a-camera>
    <a-sky color="#DDDDDD"></a-sky>
  </a-scene>
</template>

<script>
import {select} from 'd3-selection';
import {range} from 'd3-array';
export default {
  mounted() {
    const data = range(20).map((i) => ({value: (i + 1) / 10, label: `Item ${i + 1}`}))

    const entity = select('a-scene')
      .selectAll('a-entity')
      .data(data)
      .enter()
      .append('a-entity')
      .attr('rotation', (datum, index) => {
        return `0 ${(60 + index * -7)} 0`;
      });

    entity.append('a-box')
      .attr('material', 'color:#08c;')
      .attr('width', 0.4)
      .attr('height', ({value}) => value)
      .attr('position', ({value}) => {
        return `0 ${value / 2} -5`
      });

    entity.append('a-entity')
      .attr('text', ({label}) => `value: ${label};color: black;align:center;`)
      .attr('position', () => {
        return `0 .1 -4`
      });
  }
}
</script>
