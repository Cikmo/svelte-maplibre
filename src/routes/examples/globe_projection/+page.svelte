<script lang="ts">
    import MapLibre from '$lib/MapLibre.svelte';
    import CodeSample from '$site/CodeSample.svelte';
    import code from './+page.svelte?raw';
    import { GlobeControl } from 'maplibre-gl';
  </script>
  
  <MapLibre
    style="https://basemaps.cartocdn.com/gl/positron-gl-style/style.json"
    class="relative aspect-[9/16] max-h-[70vh] w-full sm:aspect-video sm:max-h-full"
    standardControls
    onload={(map) => {
      map.addControl(new GlobeControl(), 'top-right');
    }}
  />
  
  <CodeSample
    {code}
    startBoundary="<MapLibre"
    endBoundary="/>"
    omitStartBoundary={false}
    omitEndBoundary={false}
  />
  