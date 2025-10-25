<script lang="ts">
  import "./app.css";
  import { Map, TileLayer } from 'sveaflet';
  import PubSearch from "./lib/components/ui/pub-search.svelte";
  
  const pubs = [
    { value: "pub1", label: "Pub 1" },
    { value: "pub2", label: "Pub 2" },
    { value: "pub3", label: "Pub 3" }
  ];
  
  let selectedPub = $state("pub1");
  let query = $state("")
</script>

<div style="display:flex; width:100%; height:100%; position:relative; justify-content:center;">  
  <PubSearch bind:value={query} {pubs}/>

  <Map
    options={{
      center: [50,0],
      zoom: 5
    }}
  >
    <TileLayer url={'https://tile.openstreetmap.org/{z}/{x}/{y}.png'} />
  </Map>
</div>
