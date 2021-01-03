<template>
  <div class="container">
    <p
      v-for="podcast of podcasts.times"
      :key="podcast"
      class="podcast"
      @click="clickPodcast(podcast)"
    >
      {{ podcast }}
    </p>
    <p>Click a friend</p>
  </div>
</template>

<script lang="ts">
import { reactive } from '@vue/composition-api'

export default {
  setup() {
    const podcasts = reactive({
      times: [
        'Angular Air is aired on Friday at 1am',
        'Angular Dutch is aired on Thursday at 1:30am',
        'Angular APAC is aired on Wednesday at 9:00pm',
        'ngHouston is aired on Wednesday at 1:00am',
      ],
    })

    function clickPodcast(podcast: string) {
      alert(podcast)
    }

    return {
      podcasts,
      clickPodcast,
    }
  },
}
</script>

<style lang="scss" scoped>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;

  .podcast {
    cursor: pointer;
    margin: 0.5rem;
  }
}
</style>
