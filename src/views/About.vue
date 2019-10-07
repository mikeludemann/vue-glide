<template>
  <div class="about">
    <GlideSlider 
      id="main-slider"
      options="{
        type: 'slider',
        width: 400,
        autoheight: true,
        startAt: 0,
        autoplay: 2500,
        breakpoints: {
          576: {
            perView: 1
          },
          768: {
            perView: 2
          },
          992: { 
            perView: 3
          },
          1200: { 
            perView: 3
          }
        }
      }"
    >
      <SliderContainer>
        <SliderElement>
          <div className="custom--slide">
            My name is ...
          </div>
        </SliderElement>
        <SliderElement>
          <div className="custom--slide">
            1 - 1
          </div>
        </SliderElement>
        <SliderElement>
          <div className="custom--slide">
            2 - 1
          </div>
        </SliderElement>
      </SliderContainer>
      <Controls></Controls>
      <Dots></Dots>
    </GlideSlider>
  </div>
</template>

<script>
import { Component, Vue } from 'vue-property-decorator';
import { GlideSlider, Controls, SliderContainer, SliderElement, Dots } from '@/components/glide.vue'; // @ is an alias to /src

@Component({
  components: {
    GlideSlider,
    Controls,
    SliderContainer,
    SliderElement,
    Dots,
  },
})
export default class About extends Vue {}
</script>
