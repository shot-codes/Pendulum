<script lang="ts">
  import { T, useTexture } from "@threlte/core";
  import { Attractor } from "@threlte/rapier";
  import { DEG2RAD } from "three/src/math/MathUtils";

  const mapRadius = 6;
  const magnetOffset = 0.5;
</script>

<!-- Magnets -->
<T.Group
  position={[
    Math.cos((2 * Math.PI) / 5) * (mapRadius - magnetOffset),
    1,
    Math.sin((2 * Math.PI) / 5) * (mapRadius - magnetOffset),
  ]}
>
  <Attractor range={3} />
  <T.Mesh>
    <T.CylinderGeometry args={[1.2, 1.2, 0.4]} />
    <T.MeshStandardMaterial color={"#aa2222"} />
  </T.Mesh>
</T.Group>

<T.Group
  position={[
    Math.cos((4 * Math.PI) / 5) * (mapRadius - magnetOffset),
    1,
    Math.sin((4 * Math.PI) / 5) * (mapRadius - magnetOffset),
  ]}
>
  <Attractor range={3} strength={-1} />
  <T.Mesh>
    <T.CylinderGeometry args={[1.2, 1.2, 0.4]} />
    <T.MeshStandardMaterial color={"#2222aa"} />
  </T.Mesh>
</T.Group>

<T.Group
  position={[
    Math.cos((6 * Math.PI) / 5) * (mapRadius - magnetOffset),
    1,
    Math.sin((6 * Math.PI) / 5) * (mapRadius - magnetOffset),
  ]}
>
  <Attractor range={3} />
  <T.Mesh>
    <T.CylinderGeometry args={[1.2, 1.2, 0.4]} />
    <T.MeshStandardMaterial color={"#aa2222"} />
  </T.Mesh>
</T.Group>

<T.Group
  position={[
    Math.cos((8 * Math.PI) / 5) * (mapRadius - magnetOffset),
    1,
    Math.sin((8 * Math.PI) / 5) * (mapRadius - magnetOffset),
  ]}
>
  <Attractor range={3} strength={-1} />
  <T.Mesh>
    <T.CylinderGeometry args={[1.2, 1.2, 0.4]} />
    <T.MeshStandardMaterial color={"#2222aa"} />
  </T.Mesh>
</T.Group>

<T.Group
  position={[
    Math.cos((10 * Math.PI) / 5) * (mapRadius - magnetOffset),
    1,
    Math.sin((10 * Math.PI) / 5) * (mapRadius - magnetOffset),
  ]}
>
  <Attractor range={3} />
  <T.Mesh>
    <T.CylinderGeometry args={[1.2, 1.2, 0.4]} />
    <T.MeshStandardMaterial color={"#aa2222"} />
  </T.Mesh>
</T.Group>

<!-- Map -->
<T.Mesh receiveShadow rotation.x={270 * DEG2RAD} position.y={0.3}>
  <T.CircleGeometry args={[mapRadius, 72]} />
  <T.MeshStandardMaterial map={useTexture("earth.png")} />
</T.Mesh>
