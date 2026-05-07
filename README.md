<html lang="en">
<head>
<meta charset="UTF-8" />

<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
/>

<title>Correct Responsive Snap Scroll</title>

<style>

/* RESET */

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {

  width: 100%;
  height: 100%;

  overflow: hidden;

  font-family: Arial, sans-serif;

  background: black;
}

/* CONTAINER */

.container {

  width: 100%;
  height: 100vh;

  overflow-y: scroll;

  scroll-snap-type: y mandatory;

  scroll-behavior: smooth;
}

/* PANELS */

.panel {

  width: 100%;
  height: 100vh;

  scroll-snap-align: start;

  display: flex;
  justify-content: center;
  align-items: center;

  padding: 20px;
}

/* INNER CONTENT WRAPPER */

.content {

  width: 100%;

  max-width: 700px;

  display: flex;
  flex-direction: column;

  align-items: center;

  gap: 24px;
}

/* COLORS */

.dark {
  background: #000;
  color: white;
}

.light {
  background: #f5f5f5;
  color: #111;
}

.blue {
  background: #1d4ed8;
  color: white;
}

/* TEXT */

h1 {

  font-size: clamp(2rem, 5vw, 4rem);

  text-align: center;
}

p {

  font-size: clamp(1rem, 2vw, 1.3rem);

  line-height: 1.5;

  text-align: center;
}

/* MEDIA */

img,
video {

  width: 100%;

  max-width: 500px;

  max-height: 60vh;

  object-fit: contain;

  border-radius: 16px;

  display: block;
}

/* MOBILE */

@media (max-width: 768px) {

  .content {

    max-width: 100%;
  }

  img,
  video {

    max-width: 100%;

    max-height: 50vh;
  }

  h1 {

    font-size: 2rem;
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

  <section class="panel dark">

    <div class="content">

      <h1>Responsive Video</h1>

      <video
        autoplay
        muted
        loop
        playsinline
        controls
      >
        <source src="media/video1.mp4" type="video/mp4">
      </video>

      <p>
        Properly scaled for desktop and mobile.
      </p>

    </div>

  </section>

  <!-- PANEL 2 -->

  <section class="panel light">

    <div class="content">

      <h1>Text Section</h1>

      <p>
        This content stays readable and centered
        instead of stretching too large.
      </p>

    </div>

  </section>

  <!-- PANEL 3 -->

  <section class="panel blue">

    <div class="content">

      <h1>Responsive Image</h1>

      <img
        src="media/image1.jpg"
        alt="Example image"
      >

    </div>

  </section>

</div>

</body>
</html>
