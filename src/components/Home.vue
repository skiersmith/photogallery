<template>
  <div class="bg">
   <!-- <p>HS</p> -->
    <div style="height: 3rem;"></div>
    <!-- <div class="photo"> -->
    <img class="photo" src="../assets/photo1.jpg" alt="">
    <img class="photo" src="../assets/q1-6080.jpg">
    <img class="photo" src="../assets/q1-2812.jpg">
    <!-- </div> -->
    <div style="height: 15rem;">
      <transition name="fade">
        <div style="height: 1rem;">
          <h4 class="text-center" v-show="show">Thank you for visiting!</h4>
        </div>
      </transition>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'Home',
    data() {
      return {
        show: false,
        scrolled: false,
      }
    },
    created() {
      window.addEventListener('scroll', this.handleScroll);
    },
    destroyed() {
      window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
      handleScroll() {
        // console.log(window.scrollY)
        this.scrolled = window.scrollY > 150;
        // console.log(window.)
        if ($(window).scrollTop() + $(window).height() == $(document).height()) {
         
          this.show = true
        }
        else{
          // this.show = false
        }
        // if (window.scrollY < window.Screen.height) {
        //   this.show = false
        // }
        // else {
        // }
      },
    },
    computed: {

    },
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /* h1, h2 {
  font-weight: normal;
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
} */

  .photo {
    width: 100vw;
    margin: 1rem;
    padding: 1rem;
    /* height: 100vh; */
  }

  .bg {
    /* background-color: black; */
    width: 100vw;
    height: 100vh;

  }

  .fade-enter-active,
  .fade-leave-active {
    transition: opacity .5s ease-out;
  }
  .fade-enter,
  .fade-leave-to {
    opacity: 0;
  }
</style>