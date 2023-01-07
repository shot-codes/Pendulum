<script>
  import { Canvas } from "@threlte/core";
  import { Debug, World } from "@threlte/rapier";
  import Scene from "$lib/components/Scene.svelte";
</script>

<div class="w-full h-full">
  <Canvas>
    <World gravity={{ y: -100 }}>
      <Debug />
      <Scene />
    </World>
  </Canvas>
</div>
