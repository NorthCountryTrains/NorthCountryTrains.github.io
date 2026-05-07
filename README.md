# NorthCountryTrains.github.io



<html lang="en">
<head>
<meta charset="UTF-8" />
<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0, viewport-fit=cover"
/>

<title>Responsive Snap Scroll</title>

<style>

/* RESET */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* DYNAMIC MOBILE HEIGHT */

:root {
  --vh: 1vh;
}

/* PAGE */

html,
body {
  width: 100%;
  height: 100%;
  overflow: hidden;

  background: black;
  font-family: Arial, sans-serif;
}

/* SNAP CONTAINER */

.container {

  height: calc(var(--vh) * 100);

  overflow-y: auto;

  scroll-snap-type: y mandatory;

  scroll-behavior: smooth;

  -webkit-overflow-scrolling: touch;
}

/* PANELS */

.panel {

  position: relative;

  width: 100%;

  height: calc(var(--vh) * 100);

  scroll-snap-align: start;

  display: flex;
  flex-direction: column;

  justify-content: center;
  align-items: center;

  padding: 24px;

  overflow: hidden;
}

/* COLORS */

.dark {
  background: #000;
  color: white;
}

.light {
  background: #f2f2f2;
  color: #111;
}

.blue {
  background: linear-gradient(135deg, #0f172a, #2563eb);
  color: white;
}

/* TEXT */

h1 {

  font-size: clamp(2rem, 8vw, 5rem);

  text-align: center;

  margin-bottom: 20px;
}

p {

  font-size: clamp(1rem, 3vw, 1.5rem);

  line-height: 1.6;

  max-width: 800px;

  text-align: center;
}

/* MEDIA */

img,
video {

  width: min(100%, 900px);

  max-height: 75vh;

  object-fit: contain;

  border-radius: 20px;
}

/* FULLSCREEN VIDEO */

.fullscreen-video video {

  position: absolute;

  inset: 0;

  width: 100%;
  height: 100%;

  object-fit: cover;

  z-index: 1;
}

/* DARK VIDEO OVERLAY */

.fullscreen-video::after {

  content: "";

  position: absolute;

  inset: 0;

  background: rgba(0,0,0,0.35);

  z-index: 2;
}

/* CONTENT ABOVE VIDEO */

.overlay {

  position: relative;

  z-index: 3;

  padding: 20px;
}

/* MOBILE FIXES */

@media (max-width: 768px) {

  .panel {
    padding: 18px;
  }

  h1 {
    font-size: clamp(2rem, 10vw, 4rem);
  }

  p {
    font-size: 1rem;
  }

  img,
  video {

    width: 100%;

    max-height: 65vh;
  }

}

</style>
</head>

<body>

<div class="container">

  <!-- PANEL 1 -->

  <section class="panel fullscreen-video dark">

    <video
      autoplay
      muted
      loop
      playsinline
    >
      <source src="media/video1.mp4" type="video/mp4">
    </video>

    <div class="overlay">

      <h1>Snap Scroll</h1>

      <p>
        Properly responsive on mobile and desktop.
      </p>

    </div>

  </section>

  <!-- PANEL 2 -->

  <section class="panel light">

    <h1>Text Panel</h1>

    <p>
      This section scales automatically using dynamic viewport sizing.
    </p>

  </section>

  <!-- PANEL 3 -->

  <section class="panel blue">

    <h1>Image Panel</h1>

    <img
      src="media/image1.jpg"
      alt="Example"
    >

  </section>

</div>

<!-- MOBILE HEIGHT FIX -->

<script>

function setVH() {

  let vh = window.innerHeight * 0.01;

  document.documentElement.style.setProperty(
    '--vh',
    `${vh}px`
  );
}

setVH();

window.addEventListener('resize', setVH);

</script>

</body>
</html>
