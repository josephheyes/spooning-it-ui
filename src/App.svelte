<script lang="ts">
  import { Map, TileLayer} from 'sveaflet'
  import PubSelect from './lib/components/PubSelect.svelte';

  const pubs = [
    {value: "pub1", label: "Pub 1"},
    {value: "pub2", label: "Pub 2"},
    {value: "pub3", label: "Pub 3"}
  ];

  let selectedPub = $state("pub1");
</script>

<div style="width: auto;">
  <PubSelect items={pubs} value={selectedPub} />
</div>

<div style="width:500px; height:500px">
  <Map
    options={{
      center: [50,0],
      zoom: 5
    }}
  >
    <TileLayer url={'https://tile.openstreetmap.org/{z}/{x}/{y}.png'} />
  </Map>
</div>