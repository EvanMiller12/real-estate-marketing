<template>
  <div class="container-fluid">
    <nav class="navbar justify-content-between">
      <a>
        For Sale By Owner -
        <b>119 Ming Lane Anderson, SC 29625</b>
      </a>
      
      <a href="#contact">Contact Owner</a>
    </nav>
    <section id="slider">
      <!-- <header>
        <h3>3 Beds</h3>
        <h3>3 Bath</h3>
        <h3>2042 sqft</h3>
      </header>-->
      <div class="thumbnails">
        <div
          v-for="(image, index) in images"
          :key="index"
          :class="['thumbnail', (activeImage == index) ? 'active' : '']"
          @click="activateImage(index)"
        >
          <img :src="image.thumb" alt>
        </div>
      </div>
      <div class="slider-contain">
        <div class="slider-item">
          <!-- <address>119 Ming Lane, Anderson, SC 29625</address> -->
          <div class="slider-img">
            <img :src="currentImage" alt>
          </div>
        </div>
        <!-- <div class="slider-controls"> -->
        <span @click="prevImage" class="prev">
          <i class="far fa-arrow-alt-circle-left"/>
        </span>
        <span @click="nextImage" class="next">
          <i class="far fa-arrow-alt-circle-right"/>
        </span>
        <!-- </div> -->
      </div>
    </section>
    <div id="feats-container">
      <nav id="feats-nav">
        <a href="#feats">Features</a>
        <a href="#interior-feats">Interior</a>
        <a href="#exterior-feats">Exterior</a>
        <a href="#contact">Location</a>
      </nav>
      <section id="feats">
        <h1>Features</h1>
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloremque nemo quaerat excepturi fuga labore nihil nostrum veniam ex cupiditate cum temporibus, exercitationem delectus reprehenderit, ipsa, velit consequuntur autem ab eveniet?</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ea placeat repellat distinctio earum voluptas mollitia ducimus ipsa tenetur sunt hic nesciunt fugit, laboriosam, architecto dolor beatae esse alias commodi accusantium!</p>
      </section>
      <section id="interior-feats">
        <h1>Interior</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias dicta magni assumenda deserunt beatae illum ut blanditiis minima doloremque numquam labore delectus nemo eveniet facere quia dolores, reprehenderit minus aperiam?</p>
      </section>
      <section id="exterior-feats">
        <h1>Exterior</h1>
      </section>
      <section id="contact">
        <h1>Features</h1>
      </section>
    </div>
    <footer>
      <a href="#">&copy; Evan Miller 2019</a>
    </footer>
  </div>
</template>

<script>
// import Carousel from '~/components/Carousel.vue'

export default {
  components: {
    // Carousel
  },
  data() {
    return {
      images: [
        {
          id: '1',
          big: 'https://via.placeholder.com/850x570',
          thumb: 'https://via.placeholder.com/180x150'
        },
        {
          id: '2',
          big: 'https://via.placeholder.com/850x570',
          thumb: 'https://via.placeholder.com/180x150'
        },
        {
          id: '3',
          big: 'https://via.placeholder.com/850x570',
          thumb: 'https://via.placeholder.com/180x150'
        },
        {
          id: '4',
          big: 'https://via.placeholder.com/850x570',
          thumb: 'https://via.placeholder.com/180x150'
        }
      ],
      activeImage: 0
    }
  },
  computed: {
    currentImage() {
      return this.images[this.activeImage].big
    }
  },
  methods: {
    nextImage() {
      let active = this.activeImage + 1
      if (active >= this.images.length) {
        active = 0
      }
      this.activateImage(active)
    },
    prevImage() {
      let active = this.activeImage - 1
      if (active < 0) {
        active = this.images.length - 1
      }
      this.activateImage(active)
    },
    activateImage(imageIndex) {
      this.activeImage = imageIndex
    }
  }
}
</script>

<style>
body {
  font-size: 10px;
}
h1 {
  font-size: 5em;
}

h2 {
  font-size: 4em;
}

a {
  font-size: 1.8em;
}
section {
  padding: 50px 0;
}

header {
  text-align: center;
}

/* h2 {
  position: absolute;
  top: -39px;
} */
.navbar {
  border-bottom: 1px solid lightGrey;
}
#slider {
  display: flex;
  /* justify-content: center; */
}

.slider-content {
  /* padding: 10px 0; */
  text-align: center;
}

span i:hover,
.thumbnail:hover {
  cursor: pointer;
}

.slider-img img {
  border-radius: 3px;
}

.slider-contain {
  position: relative;
}

.prev,
.next {
  position: absolute;
  bottom: 5%;
}

.prev {
  left: 5%;
}

.next {
  right: 5%;
}

/* .slider-controls {
  display: flex;
  justify-content: space-around;
  text-align: center;
  padding-top: 5px;
} */

.thumbnails {
  display: flex;
  flex-direction: column;
  height: 570px;
  margin-right: 5px;
  overflow-y: scroll;
}

.thumbnail {
  margin-bottom: 5px;
}

/***
Feature Nav
**/

#feats-container {
  background-color: rgb(231, 231, 231);
}

#feats-container h1 {
  text-align: center;
}

#feats-nav {
  position: sticky;
  top: 0;
  display: flex;
  justify-content: space-around;
  padding: 15px 0;
  background-color: royalblue;
}
#feats-nav a {
  color: white;
}

.fa-arrow-alt-circle-left,
.fa-arrow-alt-circle-right {
  font-size: 50px;
}
</style>
