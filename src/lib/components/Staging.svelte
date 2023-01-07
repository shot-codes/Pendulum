<script>
  import { OrbitControls, T } from "@threlte/core";
  import { Environment } from "@threlte/extras";
  import { DEG2RAD } from "three/src/math/MathUtils";
</script>

<Environment
  path="/"
  files="bball_ultra_low_res.hdr"
  isBackground={false}
  groundProjection={{ radius: 140, height: 10, scale: { x: 150, y: 150, z: 150 } }}
  format="hdr"
/>

<T.PerspectiveCamera makeDefault position={[-20, 0, -20]} fov={50}>
  <OrbitControls maxPolarAngle={90 * DEG2RAD} target={{ y: 5 }} enableDamping />
</T.PerspectiveCamera>

<T.DirectionalLight castShadow position={[-50, 35, -60]} intensity={0.8} />
<T.DirectionalLight castShadow position={[10, 35, -70]} intensity={0.4} />
<T.AmbientLight intensity={0.2} />
