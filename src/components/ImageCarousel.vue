<template>
  <div class="image-carousel">
    <div v-if="images.length > 0" class="carousel">
      <img :src="currentImage" alt="Carousel Image" />
      <button @click="prevImage" class="prev-button">&#10094;</button>
      <button @click="nextImage" class="next-button">&#10095;</button>
    </div>
    <div v-else class="empty-carousel">
      <p>No images available</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ImageCarousel',
  props: {
    images: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      currentIndex: 0
    };
  },
  computed: {
    currentImage() {
      return this.images[this.currentIndex];
    }
  },
  methods: {
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevImage() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style>
.image-carousel {
  text-align: center;
  margin-top: 20px;
}

.carousel img {
  max-width: 100%;
}

.prev-button,
.next-button {
  cursor: pointer;
  background-color: black;
  color: white;
  border: none;
  padding: 10px;
  margin: 0 5px;
  font-size: 18px;
}

.empty-carousel {
  color: red;
}
</style>
