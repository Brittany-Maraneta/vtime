<template>
  <div class="index-container">
    <video autoplay muted loop class="background-video">
      <source
        src="https://videos.pexels.com/video-files/5874065/5874065-uhd_2732_1440_30fps.mp4"
        type="video/mp4"
      />
    </video>
    <div class="content">
      <h1>Hi BunBun</h1>
      <h2>Welcome to our Valentine website!</h2>
      <NuxtLink to="/main"
        ><button>Click here to decide our Valentine Fate</button></NuxtLink
      >
    </div>
  </div>
</template>

<style>
/* Styling the button */
button {
  text-align: center;
  font-size: 20px;
  padding: 10px 20px;
  background-color: rgb(228, 192, 181);
  color: black;
  border: none;
  border-radius: 15px;
  cursor: pointer;
  margin-top: 20px;
}

button:hover {
  background-color: #ffccf6;
  color: black;
}

h1 {
  text-align: center;
  color: rgb(0, 0, 0);
  margin: 10px;
  margin-bottom: 5em;
}

h2 {
  text-align: center;
  color: rgb(0, 0, 0);
  margin: 10px;
}

.index-container {
  position: relative;
  height: 100vh;
  width: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content {
  text-align: center;
  z-index: 1;
}

.background-video {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
}
</style>
