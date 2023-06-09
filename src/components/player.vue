<script setup>
import { onMounted, defineProps, ref } from 'vue'

const props = defineProps(['song', 'name'])
const audioPlay = ref(null)

onMounted(() => {
  const audio = new Audio(
    `/assets/player/${props.song}.mp3`
  );

  // console.dir(audio);

  audio.addEventListener(
    "loadeddata",
    () => {
      audioPlay.value.querySelector(".time .length").textContent = getTimeCodeFromNum(
        audio.duration
      );
      audio.volume = .75;
    },
    false
  );

  //click on timeline to skip around
  const timeline = audioPlay.value.querySelector(".timeline");
  timeline.addEventListener("click", e => {
    const timelineWidth = window.getComputedStyle(timeline).width;
    const timeToSeek = e.offsetX / parseInt(timelineWidth) * audio.duration;
    audio.currentTime = timeToSeek;
  }, false);

  //click volume slider to change volume
  const volumeSlider = audioPlay.value.querySelector(".controls .volume-slider");
  volumeSlider.addEventListener('click', e => {
    const sliderWidth = window.getComputedStyle(volumeSlider).width;
    const newVolume = e.offsetX / parseInt(sliderWidth);
    audio.volume = newVolume;
    audioPlay.value.querySelector(".controls .volume-percentage").style.width = newVolume * 100 + '%';
  }, false)

  //check audio percentage and update time accordingly
  setInterval(() => {
    const progressBar = audioPlay?.value?.querySelector(".progress");
    progressBar.style.width = audio.currentTime / audio.duration * 100 + "%";
    audioPlay.value.querySelector(".time .current").textContent = getTimeCodeFromNum(
      audio.currentTime
    );
  }, 500);

  //toggle between playing and pausing on button click
  const playBtn = audioPlay.value.querySelector(".controls .toggle-play");
  playBtn.addEventListener(
    "click",
    () => {
      if (audio.paused) {
        playBtn.classList.remove("play");
        playBtn.classList.add("pause");
        audio.play();
      } else {
        playBtn.classList.remove("pause");
        playBtn.classList.add("play");
        audio.pause();
      }
    },
    false
  );

  audioPlay.value.querySelector(".volume-button").addEventListener("click", () => {
    const volumeEl = audioPlay.value.querySelector(".volume-container .volume");
    audio.muted = !audio.muted;
    if (audio.muted) {
      volumeEl.classList.remove("icono-volumeHigh");
      volumeEl.classList.add("icono-volumeMute");
    } else {
      volumeEl.classList.add("icono-volumeHigh");
      volumeEl.classList.remove("icono-volumeMute");
    }
  });

});


//turn 128 seconds into 2:08
const getTimeCodeFromNum = (num) => {
  let seconds = parseInt(num);
  let minutes = parseInt(seconds / 60);
  seconds -= minutes * 60;
  const hours = parseInt(minutes / 60);
  minutes -= hours * 60;

  if (hours === 0) return `${minutes}:${String(seconds % 60).padStart(2, 0)}`;
  return `${String(hours).padStart(2, 0)}:${minutes}:${String(
    seconds % 60
  ).padStart(2, 0)}`;
}

</script>

<template>
  <div class="video">
    <div class="audio-player" ref="audioPlay">
      <div class="timeline">
        <div class="progress"></div>
      </div>
      <div class="controls">
        <div class="play-container">
          <div class="toggle-play play">
          </div>
        </div>
        <div class="time">
          <div class="current">0:00</div>
          <div class="divider">/</div>
          <div class="length"></div>
        </div>
        <div class="name">{{ props.name }}</div>
        <div class="volume-container">
          <div class="volume-button">
            <div class="volume icono-volumeHigh"></div>
          </div>

          <div class="volume-slider">
            <div class="volume-percentage"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.audio-player {
  height: 50px;
  width: 350px;
  background: #444;
  box-shadow: 0 0 20px 0 #000a;

  font-family: arial;
  color: white;
  font-size: 0.75em;
  overflow: hidden;

  display: grid;
  grid-template-rows: 6px auto;

  .timeline {
    background: white;
    width: 100%;
    position: relative;
    cursor: pointer;
    box-shadow: 0 2px 10px 0 #0008;

    .progress {
      background: coral;
      width: 0%;
      height: 100%;
      transition: 0.25s;
    }
  }

  .controls {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    padding: 0 20px;

    >* {
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .toggle-play {
      &.play {
        cursor: pointer;
        position: relative;
        left: 0;
        height: 0;
        width: 0;
        border: 7px solid #0000;
        border-left: 13px solid white;

        &:hover {
          transform: scale(1.1);
        }
      }

      &.pause {
        height: 15px;
        width: 20px;
        cursor: pointer;
        position: relative;

        &:before {
          position: absolute;
          top: 0;
          left: 0px;
          background: white;
          content: "";
          height: 15px;
          width: 3px;
        }

        &:after {
          position: absolute;
          top: 0;
          right: 8px;
          background: white;
          content: "";
          height: 15px;
          width: 3px;
        }

        &:hover {
          transform: scale(1.1);
        }
      }
    }

    .time {
      display: flex;

      >* {
        padding: 2px;
      }
    }

    .volume-container {
      cursor: pointer;

      .volume-button {
        height: 26px;
        display: flex;
        align-items: center;

        .volume {
          transform: scale(0.7);
        }
      }

      position: relative;
      z-index: 2;

      .volume-slider {
        position: absolute;
        left: -3px;
        top: 15px;
        z-index: -1;
        width: 0;
        height: 15px;
        background: white;
        box-shadow: 0 0 20px #000a;
        transition: 0.25s;

        .volume-percentage {
          background: coral;
          height: 100%;
          width: 75%;
        }
      }

      &:hover {
        .volume-slider {
          left: -123px;
          width: 120px;
        }
      }
    }
  }
}

@media screen and (max-width: 800px) {
  .audio-player {
    width: auto;
  }
}
</style>
