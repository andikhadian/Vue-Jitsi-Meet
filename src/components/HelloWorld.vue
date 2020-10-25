<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <vue-jitsi-meet ref="jitsiRef" domain="meet.jit.si" :options="jitsiOptions"></vue-jitsi-meet>
  </div>
</template>

<script>
import { JitsiMeet } from "@mycure/vue-jitsi-meet";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    VueJitsiMeet: JitsiMeet
  },
  computed: {
    jitsiOptions() {
      return {
        roomName: "KELAS VIIA",
        noSSL: false,
        width: 1000,
        height: 700,
        prejoinPageEnabled: false,
        userInfo: {
          email: "user@email.com",
          displayName: "andikha"
        },
        configOverwrite: {
          enableNoisyMicDetection: false
        },
        interfaceConfigOverwrite: {
          JITSI_WATERMAK_LINK: false,
          SHOW_JITSI_WATERMARK: false,
          SHOW_WATERMARK_FOR_GUESTS: false,
          SHOW_CHROME_EXTENSION_BANNER: false
        },
        onload: this.onIFrameLoad
      };
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

#react .watermark .leftwatermark {
  display: none;
}
</style>
