<template>
  <div id="myCarousel" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#myCarousel"  v-for="image in images" v-bind:key="image.id" v-bind:data-slide-to="image.id" v-bind:class="{ active: image.isActive }"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item" v-for="image in images" v-bind:key="image.id" v-bind:class="{ active: image.isActive }" >
        <img v-bind:class="[image.isActive ? 'first-slide' : 'second-slide']" src="data:image/gif;base64,R0lGODlhAQABAIAAAHd3dwAAACH5BAAAAAAALAAAAAABAAEAAAICRAEAOw==" alt="First slide">
        <div class="container">
          <div class="carousel-caption">
            <h1>{{ image.title }}</h1>
            <p>{{ image.message }}</p>
            <p><a class="btn btn-lg btn-primary" href="#" role="button">{{ image.textbutton }}</a></p>
          </div>
        </div>
      </div>
    </div>
    <a class="carousel-control-prev" href="#myCarousel" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#myCarousel" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        images: [
          {
            id: 0,
            source: 'https://vignette.wikia.nocookie.net/marveldatabase/images/f/f7/Movie_-_Black_Panther.jpg/revision/latest/scale-to-width-down/670?cb=20180216040635',
            title: 'Example headline 1.',
            textbutton: 'Sign up today',
            message: 'Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.',
            isActive: true
          },
          {
            id: 1,
            source: 'https://vignette.wikia.nocookie.net/marveldatabase/images/a/aa/Comic_-_Infinity_Countdown.jpg/revision/latest/scale-to-width-down/670?cb=20180216045936',
            title: 'Example headline 2.',
            textbutton: 'Sign up today',
            message: 'Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.',
            isActive: false
          },
          {
            id: 2,
            source: 'https://vignette.wikia.nocookie.net/marveldatabase/images/7/74/TV_-_Marvel%27s_Jessica_Jones.jpg/revision/latest/scale-to-width-down/670?cb=20180216044740',
            title: 'Example headline 3.',
            textbutton: 'Sign up today',
            message: 'Cras justo odio, dapibus ac facilisis in, egestas eget quam. Donec id elit non mi porta gravida at eget metus. Nullam id dolor id nibh ultricies vehicula ut id elit.',
            isActive: false
          }
        ]
      }
    }
  }
</script>