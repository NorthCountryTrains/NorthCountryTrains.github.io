# NorthCountryTrains.github.io


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />

<title>Snap Scroll Multimedia Page</title>

<style>

/* RESET */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

/* GLOBAL */

html,
body {
  width: 100%;
  height: 100%;
  overflow: hidden;

  font-family: Arial, sans-serif;
  background: black;
  color: white;
}

/* SNAP CONTAINER */

.container {
  height: 100vh;
  height: 100svh;

  overflow-y: scroll;

  scroll-snap-type: y mandatory;
  scroll-behavior: smooth;

  -webkit-overflow-scrolling: touch;
}

/* EACH PANEL */

.panel {
  min-height: 100vh;
  min-height: 100svh;

  width: 100%;

  scroll-snap-align: start;

  display: flex;
  flex-direction: column;

  justify-content: center;
  align-items: center;

  position: relative;

  padding: 5vw;

  overflow: hidden;
}

/* BACKGROUND COLORS */

.dark {
  background: #000;
}

.light {
  background: #f4f4f4;
  color: #111;
}

.blue {
  background: linear-gradient(135deg, #0f172a, #1e3a8a);
}

.purple {
  background: linear-gradient(135deg, #1e1b4b, #6d28d9);
}

/* TEXT */

h1 {
  font-size: clamp(2rem, 6vw, 5rem);
  margin-bottom: 20px;
  text-align: center;
}

p {
  font-size: clamp(1rem, 2.5vw, 1.5rem);

  max-width: 900px;

  line-height: 1.6;

  text-align: center;
}

/* VIDEO */

video {
  width: min(92vw, 500px);

  max-height: 80svh;

  border-radius: 24px;

  object-fit: cover;

  box-shadow: 0 10px 40px rgba(0,0,0,0.4);
}

/* IMAGE */

img {
  width: min(92vw, 800px);

  max-height: 80svh;

  border-radius: 24px;

  object-fit: contain;

  box-shadow: 0 10px 40px rgba(0,0,0,0.4);
}

/* OVERLAY TEXT FOR FULLSCREEN VIDEO */

.overlay {
  position: absolute;

  bottom: 10%;
  left: 50%;

  transform: translateX(-50%);

  width: 90%;

  text-align: center;

  z-index: 2;

  text-shadow: 0 2px 20px rgba(0,0,0,0.7);
}

/* FULLSCREEN VIDEO SECTION */

.fullscreen-video video {
  position: absolute;

  inset: 0;

  width: 100%;
  height: 100%;

  object-fit: cover;

  border-radius: 0;

  z-index: 1;
}

/* DARK OVERLAY */

.fullscreen-video::after {
  content: "";

  position: absolute;
  inset: 0;

  background: rgba(0,0,0,0.35);

  z-index: 1;
}

/* SCROLL INDICATOR */

.scroll-indicator {
  position: absolute;

  bottom: 20px;

  font-size: 0.9rem;

  opacity: 0.7;

  animation: bounce 2s infinite;
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% {
    transform: translateY(0);
  }

  40% {
    transform: translateY(-10px);
  }

  60% {
    transform: translateY(-5px);
  }
}

/* MOBILE OPTIMIZATION */

@media (max-width: 768px) {

  .panel {
    padding: 24px;
  }

  video,
  img {
    width: 100%;
  }

  p {
    font-size: 1rem;
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
      <h1>Your Story Starts Here</h1>

      <p>
        A modern snap-scroll multimedia experience.
      </p>
    </div>

    <div class="scroll-indicator">
      ↓ Scroll ↓
    </div>

  </section>

  <!-- PANEL 2 -->
  <section class="panel light">

    <h1>Text Section</h1>

    <p>
      This section automatically adapts to desktop,
      tablet, and mobile screens using responsive sizing,
      viewport units, and flexible layouts.
    </p>

  </section>

  <!-- PANEL 3 -->
  <section class="panel blue">

    <h1>Image Showcase</h1>

    <img
      src="media/image1.jpg"
      alt="Example image"
    >

  </section>

  <!-- PANEL 4 -->
  <section class="panel purple">

    <h1>Embedded Video</h1>

    <video
      controls
      autoplay
      muted
      loop
      playsinline
    >
      <source src="media/video2.mp4" type="video/mp4">
    </video>

  </section>

  <!-- PANEL 5 -->
  <section class="panel dark">

    <h1>Final Panel</h1>

    <p>
      You can duplicate panels infinitely to build:
      portfolios, visual essays, music releases,
      documentaries, landing pages, interactive stories,
      or TikTok-style experiences.
    </p>

  </section>

</div>

</body>
</html>
