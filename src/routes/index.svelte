<script>
  import * as THREE from "three";
  import * as SC from "svelte-cubed";
  let spin = 0;

  SC.onFrame(() => {
    spin -= 0.0015;
  });
  let skills = [
    {
      name: "Frontend",
      details:
        "React, Vue, Svelte, HTML, CSS, JSX, Bootstrap, TailwindCSS, ThreeJS",
    },
    {
      name: "Backend",
      details: "NodeJS, Deno, Express, GraphQL, Firebase, Amplify",
    },
    {
      name: "Languages",
      details: "English(Fluent), Indonesian(Native), Japanese(Basic) ",
    },
    {
      name: "Design Tools",
      details:
        "Adobe Photoshop, Adobe Illustrator, Adobe XD, Figma, Live2D Cubism",
    },
    {
      name: "Cloud Technologies",
      details: "AWS, Google Cloud",
    },

    {
      name: "Databases",
      details: "SQL, MongoDB, FaunaDB, DynamoDB",
    },
    {
      name: "Artificial Intelligence",
      details: "Python, Tensorflow, Keras, Pytorch, OpenCV, GPT-3",
    },
    {
      name: "Mobile",
      details: "React Native, Flutter, Ionic, Progressive Web Apps",
    },
  ];
</script>

<div class="flex justify-center">
  <div class="m-20 p-3 w-2/4 border">
    <h1 class="text-2xl font-bold">Nicholas Robert Beckham</h1>
    <h2 class="text-lg">Full Stack Developer</h2>
    <br />

    <h1 class="text-2xl font-bold">Experience:</h1>
    <p>
      I've worked as a developer for over 3 years, with experience in both the
      backend and the frontend department. I am currently looking for a full
      time position in the field of frontend development, with the hopes of
      broadening my horizons and expanding my knowledge base.
    </p>
    <h1 class="text-2xl font-bold">Skills:</h1>

    <p>
      I am experienced in several different languages, frameworks, and
      libraries.
    </p>
    <p class="text-lg">I am familiar with the following:</p>
    {#each skills as skill}
      <p class="font-medium text-lg">{skill.name}:</p>
      <p>
        {skill.details}
      </p>
    {/each}
    <br />
    <h1 class="text-2xl font-bold">About:</h1>
    <p>
      I have a strong background in frontend development, with experience in
      HTML, CSS, and JavaScript. I have also worked with React, Vue, and Svelte.
      I have also worked with Node, Express, and MongoDB. This site is made with
      ThreeJS and Svelte. It has been engineered to be light and interactive
      even though it's a simple resume site.
    </p>
  </div>
</div>

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
    color: white;
    font-family: monospace;
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
