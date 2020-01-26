<template>
    <section class='popup'>
        <div class="content">
            <h2>{{selectedMovie.title}} <span>{{selectedMovie.year}}</span></h2>
            <p class="rating">Rating: {{selectedMovie.imdbRating}}</p>
            <div class="plot">
                <img :src="selectedMovie.Poster" alt="">
                <p>{{selectedMovie.Plot}}</p>
            </div>
            <button class="close" @click="closePopup()">Close</button>
        </div>
    </section>
</template>

<script>
export default {
  name: 'PopupDetails',
  props: ['selectedMovie'],
  data(){
    return {}
  },
  methods:{
      closePopup(){
          this.$emit('closePopup', true)
      },
  }
}
</script>

<style>
</style>
