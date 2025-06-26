<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Camera Access and Recording</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    video {
      width: 320px;
      height: 240px;
      border: 1px solid #ccc;
      margin-top: 20px;
    }
    button {
      font-size: 16px;
      padding: 10px 20px;
      margin: 10px;
      cursor: pointer;
    }
    #status {
      margin-top: 15px;
      color: #333;
    }
  </style>
</head>
<body>
  <h1>Camera Access and Recording</h1>
  <p>Click "Continue" to allow camera access and start preview.</p>
  <button id="continueBtn">Continue</button>
  <div>
    <video id="video" autoplay muted></video>
  </div>
  <div>
    <button id="recordBtn" disabled>Start Recording</button>
    <button id="stopBtn" disabled>Stop Recording</button>
  </div>
  <p id="status"></p>
  <script>
    const continueBtn = document.getElementById('continueBtn');
    const recordBtn = document.getElementById('recordBtn');
    const stopBtn = document.getElementById('stopBtn');
    const video = document.getElementById('video');
    const status = document.getElementById('status');

    let mediaStream = null;
    let mediaRecorder = null;
    let recordedChunks = [];

    continueBtn.addEventListener('click', async () => {
      status.textContent = 'Requesting camera access...';
      try {
        mediaStream = await navigator.mediaDevices.getUserMedia({ video: true });
        video.srcObject = mediaStream;
        status.textContent = 'Camera access granted. You can start recording.';
        recordBtn.disabled = false;
        continueBtn.disabled = true;
      } catch (err) {
        status.textContent = 'Camera access denied or error occurred.';
        console.error(err);
      }
    });

    recordBtn.addEventListener('click', () => {
      if (!mediaStream) return;
      recordedChunks = [];
      mediaRecorder = new MediaRecorder(mediaStream);
      mediaRecorder.ondataavailable = e => {
        if (e.data.size > 0) recordedChunks.push(e.data);
      };
      mediaRecorder.onstop = () => {
        const blob = new Blob(recordedChunks, { type: 'video/webm' });
        const url = URL.createObjectURL(blob);
        const a = document.createElement('a');
        a.style.display = 'none';
        a.href = url;
        a.download = 'recorded_video.webm';
        document.body.appendChild(a);
        a.click();
        URL.revokeObjectURL(url);
        status.textContent = 'Recording stopped. Video downloaded.';
      };
      mediaRecorder.start();
      status.textContent = 'Recording started...';
      recordBtn.disabled = true;
      stopBtn.disabled = false;
    });

    stopBtn.addEventListener('click', () => {
      if (mediaRecorder && mediaRecorder.state !== 'inactive') {
        mediaRecorder.stop();
        recordBtn.disabled = false;
        stopBtn.disabled = true;
      }
    });
  </script>
</body>
</html>
