<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: 'NeaRuS',
          imageUrl: 'nearus.png',
          status: 'This is a boarding house booking website, I made this website with 3 of my friends. My job desk for this website is front end and project manager.',
          tech: 'VueJS 3, Laravel, Tailwind',
          github: 'https://github.com/JustNandoo/nearus-project',
          demo: 'null'
        },
        {
          id: 2,
          name: 'Courtura',
          imageUrl: 'klambi_mockup.png',
          status: 'This is an online shop application, I made this as an end of semester assignment at school.',
          tech: 'Flutter',
          github: 'https://github.com/JustNandoo/PAS_Ecommerce',
          demo: 'null'
        },
        {
          id: 3,
          name: 'ELCAS Mobile',
          imageUrl: 'elcas_mockup.png',
          status: 'This is an application that I worked on during my Internship. Elcas is an application that integrates Maritime Surveillance System (Long-Range Camera, Radar, and AIS Integration).',
          tech: 'Flutter, Go Lang',
          github: 'null',
          demo: 'null'
        }
      ]
    };
  },
  computed: {
    projectsWithImages() {
      return this.items.map(item => ({
        ...item,
        imageSrc: require(`@/images/${item.imageUrl}`)
      }));
    }
  }
}
</script>
<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-10 title-section flex flex-col items-center justify-center">
          <h4>Past Project Experience</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-amber-300 text-center max-w-lg">
            Explore the projects I've worked on so far
          </h4>
        </div>
      </header>
      <section>
        <div>
          <div class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 xl:grid-cols-3 fade-zoom-in">
            <div v-for="item in projectsWithImages" :key="item.id">
              <div class="item-card flex flex-col items-center gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] text-amber-50 px-5 py-5">
                <div class="flex items-center justify-center w-[300px] h-[180px]">
                  <img :alt="item.name" :src="item.imageSrc" class="drop-shadow-xl rounded-xl object-cover w-full h-full">
                </div>
                <div class="w-full flex flex-col gap-2 items-center text-sm">
                  <div class="title-text font-medium text-secondary">{{ item.name }}</div>
                  <div class="w-full text-center text-xs text-[#c1c1c1]">{{ item.status }}</div>
                  <div class="w-full mt-4 text-sm text-center text-amber-200">{{ item.tech }}</div>
                  <div class="w-full flex justify-end">
                    <a v-if="item.github !== 'null'" :href="item.github" target="_blank" title="View Github Repository">
                      <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" height="16" width="16">
                        <path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
                      </svg>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>





<style>
.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
}
svg:hover{
  stroke: #ffdb70;
}
@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

/* Menggunakan animasi pada elemen yang diinginkan */
.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}
</style>