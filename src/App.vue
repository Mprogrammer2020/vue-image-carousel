<template>
  <div>
    <ImageCarousel :images="imageList" />
  </div>
</template>

<script>
import ImageCarousel from 'vue-carousel';

export default {
  name: 'App',
  components: {
    ImageCarousel,
  },
  data() {
    return {
      imageList: [
        'https://example.com/image1.jpg',
        'https://example.com/image2.jpg',
        'https://example.com/image3.jpg',
      ],
    };
  },
};
</script>
