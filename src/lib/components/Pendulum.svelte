<script lang="ts">
  import { T, InteractiveObject } from "@threlte/core";
  import { Vector3 } from "three";
  import { RigidBody, Collider, useSphericalJoint } from "@threlte/rapier";

  const {
    joint,
    rigidBodyA: anchorBody,
    rigidBodyB: weightBody,
  } = useSphericalJoint({ y: -0.25 }, { y: 10 });

  const randomImpulse = () => {
    const signX = Math.random() < 0.5 ? -1 : 1;
    const signZ = Math.random() < 0.5 ? -1 : 1;
    const x = Math.floor(5 + Math.random() * 60);
    const z = Math.floor(5 + Math.random() * 60);
    $weightBody?.applyImpulse(new Vector3(signX * x, 0, signZ * z), true);
  };
</script>

<RigidBody type={"fixed"} position={{ y: 12 }} bind:rigidBody={$anchorBody}>
  <Collider contactForceEventThreshold={30} restitution={0.4} shape={"ball"} args={[0.25]} />
  <T.Mesh castShadow>
    <T.SphereGeometry args={[0.25]} />
    <T.MeshStandardMaterial color="#333333" />
  </T.Mesh>
</RigidBody>

<RigidBody type={"dynamic"} bind:rigidBody={$weightBody} linearDamping={0.5}>
  <Collider contactForceEventThreshold={30} restitution={0.4} shape={"ball"} args={[1]} mass={1} />
  <T.Mesh castShadow let:ref>
    <InteractiveObject object={ref} interactive on:click={randomImpulse} />
    <T.SphereGeometry />
    <T.MeshStandardMaterial color="#333333" />
  </T.Mesh>
</RigidBody>
