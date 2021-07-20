<template>
  <div class="container mx-auto bg-white h-screen">
    <div class="max-w-7xl mx-auto py-12 px-4 text-center sm:px-6 lg:px-8 lg:py-24">
      <div class="space-y-8 sm:space-y-12">
        <div class="space-y-5 sm:mx-auto sm:max-w-xl sm:space-y-4 lg:max-w-5xl">
          <h2 class="text-3xl font-extrabold tracking-tight sm:text-4xl">Personas</h2>
          <p class="text-xl text-gray-500">Risus velit condimentum vitae tincidunt tincidunt. Mauris ridiculus fusce amet urna nunc. Ut nisl ornare diam in.</p>
        </div>
        <ul class="mx-auto grid grid-cols-2 gap-x-4 gap-y-8 sm:grid-cols-4 md:gap-x-6 lg:max-w-5xl lg:gap-x-8 lg:gap-y-12 xl:grid-cols-6">
          <li v-for="person in people" :key="person.name">
            <a href="#" @click="show(person)" class="personaCard block space-y-4">
              <img class="mx-auto h-20 w-20 rounded-full lg:w-24 lg:h-24" :src="person.imageUrl" alt="" />
              <div class="space-y-2">
                <div class="text-xs font-medium lg:text-sm">
                  <h3>{{ person.name }}</h3>
                  <p class="text-indigo-600">{{ person.role }}</p>
                </div>
              </div>
            </a>
          </li>
        </ul>
      </div>
    </div>
    <div id="personaDetail" class="absolute top-0 left-0 h-screen w-full flex justify-center items-center"
         :class="{ visibleAnim: showModal, hiddenAnim: !showModal}" @click="hide">
      <div id="modal" class="flex flex-row justify-between" style="min-height: 500px">
        <div class="column card">
          <div class="mx-auto flex-none bg-white rounded-full flex items-center justify-center mb-4" style="width: 9.6rem; height: 9.6rem">
            <img class="rounded-full w-36 h-36" :src="person.imageUrl" alt="">
          </div>
          <h2 class="text-center font-extrabold tracking-tight">{{ person.name }}</h2>
          <div class="text-base text-center text-indigo-600 -mt-3">{{ person.role }}</div>
          <div class="text-gray-400 mt-24 px-12 text-5xl italic">"</div>
          <div class="italic text-gray-600 text-center leading-7 -mt-3 px-12 py-2">
            I'm looking for a site that will simplify the planning of my business trips.
          </div>
          <div class="mt-1 text-right px-12 text-5xl italic text-gray-400">"</div>
        </div>
        <div class="column flex flex-col">
          <div class="card mb-5">
            <h2>Bio</h2>
            <p>
              Jill is a Regional Director who travels 4-8 times each month for work. She has a specific region in which she travels, and she often
              visits the same cities and stay at the same hotel.
            </p>
            <p>
              She is frustrated by the fact that no matter how frequently she takes similar trips, she spends hours of her day for booking travel.<br>
            </p>
            <p>
              She expects her travel solutions to be as organized as she is.
            </p>
          </div>
          <div class="card flex-1">
            <h2>Goals</h2>
            <ul>
              <li>To spend less time booking travel</li>
              <li>To narrow her options quickly</li>
            </ul>
          </div>
        </div>
        <div class="column flex flex-col">
          <div class="card mb-5">
            <h2>Frustration</h2>
            <ul>
              <li>To much time spend booking - she is busy!</li>
              <li>To many website visited per trip</li>
              <li>Not teribbly tech savvy - doesn't like the process</li>
            </ul>
          </div>
          <div class="card flex-1">
            <h2>Personality</h2>
            <slider left-label="Introvert" right-label="Extrovert" percent="30" class="mb-5 mt-6"/>
            <slider left-label="Analytical" right-label="Creative" percent="85" class="mb-5"/>
            <slider left-label="Loyal" right-label="Fickle" percent="10" class="mb-5"/>
            <slider left-label="Passive" right-label="Active" percent="60" class="mb-5"/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import Slider from './components/Slider.vue'

const people = [
  {
    name: 'Michael Foster',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1519244703995-f4e0f30006d5?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Dries Vincent',
    role: 'Manager, Business Relations',
    imageUrl:
        'https://images.unsplash.com/photo-1506794778202-cad84cf45f1d?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Lindsay Walton',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1517841905240-472988babdf9?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Michael Foster',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Michael Foster',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Michael Foster',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1517365830460-955ce3ccd263?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Michael Foster',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1519345182560-3f2917c472ef?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  },
  {
    name: 'Michael Foster',
    role: 'Co-Founder / CTO',
    imageUrl:
        'https://images.unsplash.com/photo-1463453091185-61582044d556?ixlib=rb-=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=8&w=1024&h=1024&q=80',
  }
  // More people...
];

export default defineComponent({
  name: 'App',
  components: {
    Slider
  },
  setup() {
    return {
      people,
      person: ref({}),
      showModal: ref(false)
    }
  },
  methods: {
    show(person) {
      this.person = person;
      this.showModal = true;
    },
    hide() {
      this.showModal = false;
    }
  }
})
</script>

<style>
#app {
  @apply relative subpixel-antialiased;
}
.personaCard:hover img {
  @apply transition transform -translate-x-1 -translate-y-1
}
.personaCard:hover h3 {
  @apply underline
}

#personaDetail {
  @apply bg-white;
  top: 0;
  left: 0;
  z-index: 1000;
}

#modal {
  z-index: 1001;
  width: 1300px;
  max-width: 1300px;
  border-radius: 20px;
}

.visibleAnim {
  visibility: visible;
  opacity: 1;
  transition: opacity 200ms linear;
}

.hiddenAnim {
  visibility: hidden;
  opacity: 0;
  transition: visibility 0s 200ms, opacity 200ms linear;
}

#modal ul li::before {
  content: "\2022";  /* Add content: \2022 is the CSS Code/unicode for a bullet */
  @apply text-indigo-500 ;
  font-weight: bold; /* If you want it to be bold */
  display: inline-block; /* Needed to add space between the bullet and the text */
  width: 1em; /* Also needed for space (tweak if needed) */
  margin-left: -1em; /* Also needed for space (tweak if needed) */
}

.column {
  width: 32%;
}
.card {
  @apply bg-gradient-to-br from-indigo-50 to-indigo-100 rounded-lg shadow p-8;
}
.card p {
  @apply my-2 text-gray-600;
}

.card ul {
  @apply list-none list-outside transform translate-x-4 mb-4 pr-10;
}

.card ul li {
  @apply text-gray-600 py-1;
}

.card h2 {
  @apply text-xl font-extrabold tracking-tight mt-0 mb-4;
}
</style>
