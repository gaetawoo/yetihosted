<template>
  <div>
    <navbarcold></navbarcold>
    <div class="container" style="margin-top: 3rem;">
      <h2></h2>
      <div class="hero-unit">
          <h1>Yeti Cold Storage</h1>
          <p>Yeti Cold Storage is recommended for more than $50,000 USD worth of bitcoin. It is a 3 of 7 HD multisig setup where private keys are never on an internet connected device.</p>
          <p>
            <input v-on:click="Cold" style="margin-bottom:50px;" class="btn btn-primary btn-large" type="submit" id="next" value="Yeti Cold">
          </p>
      </div>
      <div class="hero-unit">
          <h1>Yeti Warm Storage</h1>
          <p>Yeti Warm Storage is recommended for storing between $5,000 and $50,000 USD worth of bitcoin. It is a 3 of 7 HD multisig setup that requires only a single computer to setup.</p>
          <p>
            <input v-on:click="Warm" style="margin-bottom:50px;" class="btn btn-warning btn-large" type="submit" id="next" value="Yeti Warm">
          </p>
      </div>
      <div class="hero-unit">
          <h1>Yeti Hot Storage</h1>
          <p>Yeti Hot Storage is recommended for storing under $5,000 USD worth of bitcoin. It is very easy to backup and restore and requires only a single computer to setup.</p>
          <p>
            <input v-on:click="Hot" style="margin-bottom:50px;" class="btn btn-danger btn-large" type="submit" id="next" value="Yeti Hot">
          </p>
      </div>
      <a style="margin-top:30px;margin-bottom:30px;color:#585858;text-decoration: underline;" href="" v-on:click="Utils">Yeti Utilites</a>
      <p></p>
      <p style="color:light-gray;">For more information and the source code click <a href="https://github.com/JWWeatherman/yeticold">here</a> for the GitHub repo.</p>
    </div>
  </div>
</template>

<script>
import navbarcold from './navbarcold'
export default {
  mounted () {
    let host = window.location.host.toUpperCase()
    if (host === 'COLD.YETICOLD.COM') {
      this.$router.push({path: '/Cold/step4'})
    }else if (host === 'WARM.YETICOLD.COM') {
      this.$router.push({path: '/Warm/step4'})
    }else if (host === 'HOT.YETICOLD.COM') {
      this.$router.push({path: '/Hot/step4'})
    }else if (host === 'BCO.YETICOLD.COM') {
      this.$router.push({path: '/BCO/step4'})
    }else if (host === 'REC.YETICOLD.COM') {
      this.$router.push({path: '/Cold/Recovery/step6'})
    }else if (host === 'DISC.YETICOLD.COM') {
      this.$router.push({path: '/Cold/step6'})
    }else if (host === 'OFF.YETICOLD.COM') {
      this.$router.push({path: '/BCO/step6'})
    }
  },
  methods: {
    Utils () {
      this.$router.push({path: '/Utils'})
    },
    Cold () {
      this.$router.push({path: '/Cold/step1'})
    },
    Warm () {
      this.$router.push({path: '/Warm/step1'})
    },
    Hot () {
      this.$router.push({path: '/Hot/step1'})
    }
  },
  components: {
    navbarcold
  }
}
</script>
