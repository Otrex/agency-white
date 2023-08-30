<template> 
<div class="b-wrapper"> 
  <div class="pt-[9rem]"> 
    <h1 class="text-center max-w-[106rem] m-auto mb-[2rem]">{{ hero.headline }}</h1>
    <p class="font-jakarta text-center lg max-w-[106rem] m-auto">{{ hero.subHeadline }}</p>
    <div class="text-center mt-[3.6rem]"> 
      <a class="b-btn md accent" :href="hero.btnLink">Get Started</a>
    </div>
    <div class="bg-video py-[5rem]">
      <iframe
        class="max-w-[70rem] m-auto w-full aspect-video rounded-[2rem]"
        :data-src="hero.videoUrl"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        :src="hero.videoUrl"
        vnb-frameid="4576"
      ></iframe>
    </div>
  </div>

</div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>();

const hero = computed(() => {
  const headline = props.data?.agency_wizard.contact.introduction.intro_headline || "Unleash Your Brand Potential With Marketing Done Right";
  const subHeadline = props.data?.agency_wizard.contact.introduction.intro_desc || "Leverage Our Exceptional Services to boost your Online Business growth.";
  const btnLink = props.data?.agency_wizard.contact.introduction.intro_cta_button_link || "#";
  const videoUrl = props.data?.agency_wizard.contact.introduction.intro_video_url || "https://www.youtube.com/embed/s_o9v2EatW8?feature=oembed"
  return { headline, subHeadline, btnLink, videoUrl }
})
</script>

<style scoped> 
.bg-video {
  background: url(/img/video-bg.svg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
} 
</style>