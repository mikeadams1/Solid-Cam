# Solid-Cam
Solid_Cam can be used for various purposes, such as taking photos, video chat, live streaming video, ect..
<h1>Solid Cam</h1>
</p>
</p>
<video id="player" controls autoplay></video>
<button id="capture">Capture</button>
<canvas id="canvas" width=320 height=240></canvas>
<script>
  const player = document.getElementById('player');
  const canvas = document.getElementById('canvas');
  const context = canvas.getContext('2d');
  const captureButton = document.getElementById('capture');

  const constraints = {
    video: true,
  };

  captureButton.addEventListener('click', () => {
    // Draw the video frame to the canvas.
    context.drawImage(player, 0, 0, canvas.width, canvas.height);
  });

  // Attach the video stream to the video element and autoplay.
  navigator.mediaDevices.getUserMedia(constraints)
    .then((stream) => {
      player.srcObject = stream;
    });
</script>
