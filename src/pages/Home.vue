<template>
  <div class="content">
    <div v-if="spinner">
      <center>
        <md-progress-spinner class="md-primary centerSpinner" :md-stroke="3" md-mode="indeterminate"></md-progress-spinner>
      </center>
    </div>
    <div v-else class="animated fadeInUp">
      <div class="jumbo">
        <img src="../assets/img/zhen-hu-340739.jpg" alt="" class="jumboImg">
        <div class="welcomeNote">
          <div class="welcomeTitle">
            <span class="md-display-3">Welcome To MedFind</span>
          </div>
          <div class="welcomeSub">
            <span class="md-subheading">Eaisest way to locate a  hospital in less than a minute! </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data: () => ({
    msg: 'Welcome to MedFind Home Page!',
    spinner: true
  }),
  methods: {
    spinnerShow (spinner) {
      setTimeout((spinner) => {
        this.spinner = false
      }, 2000)
    }
  },
  mounted: function () {
    this.spinnerShow()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .centerSpinner{
    margin: 250px 0 250px 0;
  }
  .jumbo{
    position: relative;
    height: 300px;
  }
  .jumboImg{
    position: absolute;
    height: 100%;
    width: 100%;
    top: 50;
    left: 0;
    -o-object-fit: cover;
    object-fit: cover;
    z-index: -1;
    -webkit-filter: brightness(0.7);
    filter: brightness(0.7)
  }

  .welcomeNote{
    padding: 10px;
    text-align: center;
    color: #fff;
    font-weight: bold;
  }

</style>
