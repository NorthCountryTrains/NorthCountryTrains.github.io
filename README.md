<html lang="en">
<head>
<meta charset="UTF-8" />

<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
/>

<title>Fullscreen Snap Experience</title>

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

/* INTRO SCREEN */

.intro {

  position: fixed;

  inset: 0;

  background: #000;

  color: white;

  display: flex;
  flex-direction: column;

  justify-content: center;
  align-items: center;

  gap: 24px;

  z-index: 1000;

  transition: opacity 0.5s ease;
}

.intro.hidden {

  opacity: 0;

  pointer-events: none;
}

/* BUTTON */

.enter-button {

  padding: 16px 32px;

  font-size: 1rem;

  border: none;

  border-radius: 999px;

  background: white;

  color: black;

  cursor: pointer;

  transition: transform 0.2s ease;
}

.enter-button:hover {

  transform: scale(1.05);
}

/* SNAP CONTAINER */

.container {

  width: 100%;
  height: calc(100dvh - 100px);

  overflow-y: scroll;

  scroll-snap-type: y mandatory;

  scroll-behavior: smooth;

  display: none;
}

/* ACTIVE STATE */

.container.active {

  display: block;
}

/* PANEL */

.panel {

  width: 100%;
  height: calc(100dvh - 100px);

  scroll-snap-align: start;

  display: flex;

  justify-content: center;
  align-items: center;

  overflow: hidden;
}

/* CONTENT */

.content {

  width: 100%;
  max-width: 700px;

  height: 100%;

  padding: 20px;

  display: flex;
  flex-direction: column;

  align-items: center;

  gap: 16px;

  overflow: hidden;
}

/* ALL TEXT */

h1,
h2,
h3,
p,
span,
div {

  color: white;

  text-align: center;

  word-wrap: break-word;

  overflow-wrap: break-word;
}

/* HEADINGS */

h1 {

  font-size: clamp(2rem, 6vw, 4.5rem);

  line-height: 1.05;

  font-weight: 700;

  max-width: 90vw;

  text-wrap: balance;

  margin-bottom: 12px;
}

/* SUBHEADINGS */

/* RESPONSIVE H2 */

h2 {

  color: white;

  font-size: min(3vw, 14px);

  line-height: 1.1;

  text-align: center;

  max-width: min(90vw, 20ch);

  margin: 0 auto;

  text-wrap: balance;
}
/* PARAGRAPHS */

p {

  font-size: clamp(1rem, 2.2vw, 1.35rem);

  line-height: 1.5;

  max-width: min(90vw, 34ch);

  text-wrap: pretty;
}

/* MOBILE FIXES */

@media (max-width: 768px) {

  h1 {

    font-size: clamp(1.8rem, 8vw, 3rem);

    max-width: 95vw;
  }

  h2 {

   font-size: min(3vw, 14px);
  }

  p {

    font-size: 1rem;

    line-height: 1.45;

    max-width: 92vw;
  }
}
/* MEDIA AREA */

.media-wrapper {

  flex: 1;

  min-height: 0;

  width: 100%;

  display: flex;

  justify-content: center;
  align-items: center;

  overflow: hidden;
}
/* MEDIA */

img,
video {

  max-width: 100%;

  max-height: 100%;

  object-fit: contain;
}
/* PANEL COLORS */

.dark {
  background: #000;
}

.blue {
  background: #1d4ed8;
}

.purple {
  background: #6d28d9;
}

  .image-background {

  background-image: url("CP_9760_South_Willsboro.jpg");

  background-size: cover;

  background-position: left;

  background-repeat: no-repeat;
}

  .image-background::before {

  content: "";

  position: absolute;

  inset: 0;

  background: rgba(0,0,0,0.7);
}

  .content {
     min-height: 0;

  position: relative;

  z-index: 2;
}

/* MOBILE */

@media (max-width: 768px) {

  img,
  video {

    max-width: 100%;
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

<!-- INTRO SCREEN -->

<div class="intro" id="intro">

  <h1>Welcome</h1>

  <button
    class="enter-button"
    id="enterButton"
  >
    Legends of Lightning
  </button>

</div>

<!-- SNAP EXPERIENCE -->

<div class="container" id="container">

  <!-- PANEL 1 -->

 <section class="panel image-background">

    <div class="content">
     <h1> Legends of Lightning Along Lake Champlain </h1>
     <p1> By Harrison Smith </p1>



      <h2> I pause my rapid, rocky ascent for a moment, standing perfectly still to listen for any warning sounds of my quarry approaching. Part of me knows that listening is all but pointless; the snow dampens any sound that these surprisingly stealthy beasts make as they rumble up and down Lake Champlain. </h2>

     

    </div>

  </section>

  <!-- PANEL 2 -->

  <section class="panel blue">

    <div class="content">

      <h1>Responsive Text</h1>

      <p>
        This section perfectly fits desktop and mobile.
      </p>

    </div>

  </section>

  <!-- PANEL 3 -->

  <section class="panel purple">

    <div class="content">

      <h1>Responsive Image</h1>

      <div class="media-wrapper">

        <img
          src="CP_9760_South_Willsboro.jpg"
          alt="Example"
        >

      </div>

       <div class="media-wrapper">

        <video
          autoplay
          muted
          loop
          playsinline
          controls
        >
          <source src="media/video1.mp4" type="video/mp4">
        </video>

      </div>

    </div>

  </section>

</div>

<script>

/* BUTTON */

const button = document.getElementById("enterButton");

const intro = document.getElementById("intro");

const container = document.getElementById("container");

/* OPEN EXPERIENCE */

button.addEventListener("click", () => {

  intro.classList.add("hidden");

  container.classList.add("active");

});

</script>

</body>
</html>
