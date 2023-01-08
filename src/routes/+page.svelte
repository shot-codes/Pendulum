<script>
  import { nudge } from "$lib/stores";
  import { Canvas } from "@threlte/core";
  import { Debug, World } from "@threlte/rapier";
  import Scene from "$lib/components/Scene.svelte";
</script>

<div class="h-full w-full">
  <Canvas>
    <World gravity={{ y: -100 }}>
      <Debug />
      <Scene />
    </World>
  </Canvas>
</div>

<div class="fixed bottom-0 right-0 flex w-full rounded-md">
  <button
    on:click={() => {
      $nudge += 1;
    }}
    id="blurry"
    class=" m-6 mx-auto rounded bg-white/50 px-6 py-3 backdrop-blur-md"
  >
    nudge mass
  </button>
</div>
