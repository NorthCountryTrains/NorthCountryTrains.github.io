# NorthCountryTrains.github.io


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Snap Scroll Media Page</title>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    overflow: hidden;
    font-family: Arial, sans-serif;
  }

  .container {
    height: 100vh;
    overflow-y: scroll;
    scroll-snap-type: y mandatory;
  }

  section {
    height: 100vh;
    scroll-snap-align: start;

    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;

    padding: 40px;
  }

  .video-section {
    background: black;
    color: white;
  }

  video {
    width: 80%;
    max-width: 500px;
    border-radius: 16px;
  }

  .text-section {
    background: #f5f5f5;
    font-size: 2rem;
    text-align: center;
  }

  .image-section {
    background: #222;
    color: white;
  }

  img {
    width: 80%;
    max-width: 600px;
    border-radius: 16px;
  }
</style>
</head>

<body>

<div class="container">

  <section class="video-section">
    <h1>Short Video</h1>
    <video controls autoplay muted loop>
      <source src="video.mp4" type="video/mp4">
    </video>
  </section>

  <section class="text-section">
    <p>
      This is a scrolling text section.
      Each panel snaps into place.
    </p>
  </section>

  <section class="image-section">
    <h1>Image Section</h1>
    <img src="image.jpg" alt="Example image">
  </section>

</div>

</body>
</html>
