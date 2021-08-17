<template>
  <div id="app">
    {{ isPlaying }}
    <kinesis-container :audio="audio" ref="player" :playAudio="isPlaying">
      <kinesis-audio :audioIndex="10" type="depth">
        <kinesis-element>
          <button
            class="button"
            :class="isPlaying && 'button--playing'"
            @click="changeState"
          >
            hey
          </button></kinesis-element
        >
      </kinesis-audio>
    </kinesis-container>
    <!-- <kinesis-container
      audio="./assets/songs/onthedrums.mp3"
      :playAudio="playAudio"
    >
      <kinesis-audio :audioIndex="10">
        <kinesis-element
          class="kinesis-card--container"
          type="depth_inv"
          :strength="10"
        >
          <kinesis-element class="song-meta" type="scale" :strength="2">
            <h4>Opus</h4>
            <h6>Eric Prydz</h6>
          </kinesis-element>
        </kinesis-element>
        <kinesis-element
          class="play-btn circle"
          :strength="25"
          type="depth_inv"
        >
          <button @click="changeStatus">sdkjh</button>
        </kinesis-element>
      </kinesis-audio>
    </kinesis-container> -->
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},

  data() {
    return {
      audio: "./assets/songs/otd.mp3",
      isPlaying: false,
    };
  },
  methods: {
    changeState() {
      console.log(this.$refs.player);
      this.isPlaying = !this.isPlaying;
    },
  },
};
</script>

<style lang="scss">
body {
  padding: 0 !important;
  margin: 0 !important;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #e4e4e4;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  background: #141414;
  padding: 0 !important;
}
.kinesis-card--container {
  width: 480px;
  height: 350px;
  background: yellowgreen;
  background-image: url("https://lh3.googleusercontent.com/proxy/Wa7aA7KqAsWkjjZr24qC7QaB3iCTfkfkI8Nl69Yl2VpGRvdQuZd-jZtLNJsbTgdTWrFyQouvmF5MOZJ06pZ22GJ5aZJjcZilW8OnsMXgNn_F85HcfUx4Fm1Wnp33");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 15px;
  box-shadow: 13px 22px 90px -18px rgba(64, 64, 67, 1);
  -webkit-box-shadow: 13px 22px 90px -18px rgba(64, 64, 67, 1);
  -moz-box-shadow: 13px 22px 90px -18px rgba(64, 64, 67, 1);
}
.play-btn {
  width: 60px;
  height: 60px;
  background: #141414;
  border-radius: 50%;
  position: absolute;
  bottom: -20px;
  right: -20px;
  &:hover {
    border: 3px solid limegreen !important;
  }
}
.song-meta {
  position: absolute;
  bottom: 30px;
  left: 20px;
  text-align: left;
  h4,
  h6 {
    font-size: 1.8em;
    margin: 0;
    padding: 0;
  }
  h6 {
    font-size: 1em;
    color: grey;
  }
}
</style>
