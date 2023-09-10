<template> 
  <div id="testimonials" class="bg-[#311515] text-white py-[14rem]"> 
    <div >
      <h2 class="text-white text-center mb-[6.4rem]">What Our Partners Are saying</h2>

      <div class="flex sm:ml-[15%] overflow-x-auto text-black">
        <template v-for="(testimonial, idx) in testimonials" :key="idx">
          <div class="flex-none max-w-[50rem] w-full bg-white py-[5.5rem] px-[4.5rem] rounded-[2.1rem] m-4">
            <div class="mb-[4rem]"> {{ testimonial.description }} </div>
            <div class="flex items-center gap-3"> 
              <div class="w-[6.4rem] aspect-square ">
                <img :src="testimonial.image" class="w-full h-full object-cover rounded-full" alt="testimonial.image" />
              </div>
              <div>{{ testimonial.title }}</div>
            </div>
          </div>
        </template>
        
        <!-- ... more items ... -->
      </div>
      
    </div>
  </div>
</template>

<script setup lang="ts"> 
import { WizardResponse } from '~/type';
const props = defineProps<{ data?: WizardResponse }>();

const testimonials = computed(() => {
  const served = props.data?.agency_wizard.testimonials.map(s => ({
    description: s.description,
    image: s.metaImage || "",
    title: s.name,
  }))

  return (served || []).length ? served : [
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
    {
      image: "/img/help.jpeg",
      title: "John D., CEO, Tizz Company",
      description: "[COMPANY NAME] transformed our online presence, delivering exceptional results. Highly recommended!"
    },
  ]
})

</script>

<style> 
    
</style>