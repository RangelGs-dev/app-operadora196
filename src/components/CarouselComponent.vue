<template>
  <div>
    <div class="slideshow-container">
      <!-- Full-width images with number and caption text -->
      <div class="mySlides fade n1">
        <div class="numbertext">1 / 3</div>
        <img src="../assets/img1.jpg" style="width: 100%" />
        <div class="text">Caption Text</div>
      </div>

      <div class="mySlides fade n2">
        <div class="numbertext">2 / 3</div>
        <img src="../assets/img2.jpg" style="width: 100%" />
        <div class="text">Caption Two</div>
      </div>

      <div class="mySlides fade n3">
        <div class="numbertext">3 / 3</div>
        <img src="../assets/img3.jpg" style="width: 100%" />
        <div class="text">Caption Three</div>
      </div>

      <!-- Next and previous buttons -->
      <a class="prev" v-on:click="plusSlides(-1)">&#10094;</a>
      <a class="next" v-on:click="plusSlides(1)">&#10095;</a>
    </div>
    <br />

    <!-- The dots/circles -->
    <div style="text-align: center">
      <span class="dot" v-on:click="currentSlide(1)"></span>
      <span class="dot" v-on:click="currentSlide(2)"></span>
      <span class="dot" v-on:click="currentSlide(3)"></span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slideIndex: 1,
    };
  },
  name: "CarrouselComponent",
  methods: {
    plusSlides(n) {
      this.showSlides((this.slideIndex += n));
      // console.log(slideIndex += n);
    },
    // Thumbnail image controls
    currentSlide(n) {
      this.showSlides((this.slideIndex = n));
    },
    showSlides(n) {
      let i;
      let slides = document.querySelectorAll(".mySlides");
      let dots = document.querySelectorAll(".dot");
      if (n > slides.length) {
        console.log("Passou");
        this.slideIndex = 1;
      }
      if (n < 1) {
        this.slideIndex = slides.length;
        console.log(this.slideIndex);
      }
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
        // console.log(slides[i])
      }
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(" active", "");
      }

      slides[this.slideIndex - 1].style.display = "block";
      // console.log(slides[this.slideIndex - 1])
      dots[this.slideIndex - 1].className += " active";
      console.log(i);
    },
  },
  mounted() {
    this.showSlides(1)
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}

/* Slideshow container */
.slideshow-container {
  max-width: 900px;
  position: relative;
  margin: auto;
}

/* Hide the images by default */
.mySlides {
  display: none;
}

/* Next & previous buttons */
.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  margin-top: -22px;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover,
.next:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 100%;
  text-align: center;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* The dots/bullets/indicators */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active,
.dot:hover {
  background-color: #717171;
}

/* Fading animation */
.fade {
  animation-name: fade;
  animation-duration: 1.5s;
}

@keyframes fade {
  from {
    opacity: 0.4;
  }
  to {
    opacity: 1;
  }
}
</style>