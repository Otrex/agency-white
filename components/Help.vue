<template> 
<div> 
  <div class="b-wrapper py-[5rem] pb-[10rem]">
    <h2 class="text-center mb-[12rem] text-black">How can we help you?</h2>

    <div class="flex sm:flex-row flex-col gap-[3rem]"> 
      <div class="w-full">
        <div class="max-w-[60rem]"> 
          <h3 class="mb-[4rem]">{{ help.title }}</h3>
          <div v-html="help.description"></div>
          <div class="mt-[6rem]"> 
            <a class="b-btn md accent">Contact Us</a>
          </div>
        </div>
      </div>
      <div class="w-full relative">
        <div class="aspect-square relative z-1 w-[calc(100%_-_2.6rem)] b-st rounded-[2.8rem]">
          <img :src="help.image" class="w-full h-full object-cover rounded-[2.8rem]" alt="help" />
          <img src="/img/bubble.svg" class="absolute bottom-[-4rem] left-[5rem]" />
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>();

const help = computed(() => {
  const title = props.data?.agency_wizard.contact.help.help_headline || `Empowering Your Digital Success with [COMPANY NAME]: Expert Solutions for the Digital Age.`;
  const description = props.data?.agency_wizard.contact.help.help_desc || `
    <p class="mb-[2rem]">At [COMPANY NAME], we understand that navigating the complexities of the digital age can be daunting. That's why our team of experts is dedicated to helping you succeed. Whether you're a small business owner, an entrepreneur, or a busy professional, we offer a wide range of services that cover every aspect of your online presence.</p>
    <p>At [COMPANY NAME], we understand that navigating the complexities of the digital age can be daunting. That's why our team of experts is dedicated to helping you succeed. Whether you're a small business owner, an entrepreneur, or a busy professional, we offer a wide range of services that cover every aspect of your online presence.</p>
  `;
  const image = props.data?.agency_wizard.contact.help.help_image || "/img/help.jpeg"
  return { title, description, image }
})
</script>

<style> 
    
</style>