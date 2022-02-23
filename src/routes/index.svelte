<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  let spin = 0;

  SC.onFrame(() => {
    spin -= 0.0015;
  });
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=VT323&display=swap"
  rel="stylesheet"
/>
<h1>Nicholas Robert Beckham</h1>
<h2>Full Stack Developer</h2>

<h1>Experience:</h1>
<h1>Skills:</h1>
<h1>About:</h1>







<div class="canvas">
  <SC.Canvas antialias background={new THREE.Color("black")} class="canvas">
    <SC.Mesh
      geometry={new THREE.SphereGeometry(5, 25, 25)}
      material={new THREE.MeshStandardMaterial({
        color: "green",
        wireframe: true,
        wireframeLinewidth: 2,
        luminosity: 0.5,
      })}
      rotation={[-4, spin, 0]}
    />

    <SC.PerspectiveCamera position={[10, 0, 10]} />
    <SC.OrbitControls enableZoom={false} />
    <SC.AmbientLight intensity={0.6} />
    <SC.DirectionalLight intensity={0.6} position={[-2, 3, 2]} />
  </SC.Canvas>
</div>

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    color: #03a062;
    font-family: "VT323", monospace;
  }
  .canvas {
    width: 100vw;
    height: 100vh;
    display: block;
    position: fixed;
    top: 0;
    left: 0;
    z-index: -9999;
  }
</style>
