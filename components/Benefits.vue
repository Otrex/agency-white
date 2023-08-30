<template> 
  <div class="py-[17rem] text-black">
    <div class="b-wrapper">
      <h2 class="max-w-[73rem] mb-[8rem] m-auto text-center">Benefits of {{agencyName}} Services</h2>
      <div class="border-2 px-[5rem] py-[3rem] border-[#FFD6D4] border-solid rounded-[4rem] gap-[3rem]"> 
        <div class="w-full grid sm:grid-cols-2 gap-y-[3rem] gap-x-[10rem]">
          <template v-for="(benefit, idx) in benefits" :key="idx" >
            <div class="py-[2.3rem] px-[1.6rem]">
              <p class=" font-bold mb-[1rem]">{{ benefit.title }}</p>
              <p>{{ benefit.description }}</p>
            </div>
          </template>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>();

const agencyName = computed(() => props.data?.agency_wizard.website_details.agencyName || 'Our')
const benefits = computed(() => {
  const served = props.data?.agency_wizard.service_benefits.map(e => ({
    description: e.description,
    title: e.name,
  }));

  return (served || []).length ? served : [
    {
      title: "Expertise",
      description: "Our seasoned professionals bring 15years+ of industry experience to the table."
    },
    {
      title: "Targeted Engagement",
      description: "With our unique voice, we connect with your audience, driving loyalty and relationships from your customers so they keep coming back."
    },
    {
      title: "Comprehensive Services",
      description: "Our seasoned professionals bring 15years+ of industry experience to the table."
    },
    {
      title: "Results-Driven",
      description: "Our seasoned professionals bring 15years+ of industry experience to the table."
    },
    {
      title: "Long-Term Partnership",
      description: "We aim to become your trusted long-term marketing partner."
    },
    {
      title: "Increased Visibility",
      description: "Our seasoned professionals bring 15years+ of industry experience to the table."
    },
  ]
});
</script>

<style> 
    
</style>