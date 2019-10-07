<template lang="html">
  <section id="glide--container">
    
  </section>
</template>

<script>
import Vue from "vue";
import Glide from '@glidejs/glide';

import '@glidejs/glide/dist/css/glide.core.min.css';
import '@glidejs/glide/dist/css/glide.theme.min.css';

const GlideSlider = Vue.component('GlideSlider', {
  props: {
    id: {
      type: String
    },
    options: {
      type: Object
    }
  },
  mounted() {
    this.initGlide();
  },
  data() {
    return {

    }
  },
  methods: {
    initGlide: function(){

      var Slider = new Glide('#' + this.id, this.options)

      Slider.mount();

    }
  },
  computed: {

  },
  template: `
    <div class="glide" :id="id">
      <slot></slot>
    </div>
  `
});

const Controls = Vue.component('Controls', {
  props: {},
  mounted() {
    
  },
  data() {
    return {

    }
  },
  methods: {
    
  },
  computed: {

  },
  template: `
    <div data-glide-el="controls">
      <button class="glide__arrow glide__arrow--left" data-glide-dir="<">&larr;</button>
      <button class="glide__arrow glide__arrow--right" data-glide-dir=">">&rarr;</button>
    </div>
  `
});

const SliderContainer = Vue.component('SliderContainer', {
  props: {},
  mounted() {
    
  },
  data() {
    return {

    }
  },
  methods: {
    
  },
  computed: {

  },
  template: `
    <div class="glide__track" data-glide-el="track">
      <ul class="glide__slides">
        <slot></slot>
      </ul>
    </div>
  `
});

const SliderElement = Vue.component('SliderElement', {
  props: {},
  mounted() {
    
  },
  data() {
    return {

    }
  },
  methods: {
    
  },
  computed: {

  },
  template: `
    <li class="glide__slide">
      <slot></slot>
    </li>
  `
});

const Dots = Vue.component('Dots', {
  props: {},
  mounted() {
    document.addEventListener("DOMContentLoaded", this.info());
  },
  data() {
    return {

    }
  },
  methods: {
    info: function(){

      var container = document.getElementsByClassName("glide__slides")[0];
      var element = container.getElementsByClassName("glide__slide").length;

      var dotsContainer = document.getElementsByClassName("glide__bullets")[0];

      for(var i = 0; i < element; i++){

        var button = document.createElement("button");
        button.setAttribute("class", "glide__bullet");
        button.setAttribute("data-glide-dir", "=" + i);

        dotsContainer.appendChild(button);

      }
      
    }
  },
  computed: {

  },
  template: `
    <div class="glide__bullets" data-glide-el="controls[nav]"></div>
  `
});

export default {
  name: 'glide--container',
  components: {
    GlideSlider,
    Controls,
    SliderContainer,
    SliderElement,
    Dots
  }
}
</script>

<style scoped lang="scss">
  .glide {

  }
</style>
