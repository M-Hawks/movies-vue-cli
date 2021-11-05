<template>
<div>
  <div class="input">
    <form class="submit">
      <label>Enter keyword(s)</label>
        <div>
          <form v-on:submit.prevent="findResults">
          <input id="movieInput" type="text" v-model="searchText">
          <input id="movieSubmit" type="submit" value="Submit">
          </form>
        </div>
    </form>
  </div>

</div>
</template>


<script>

export default {
  name: 'Search',
  components: {

  },
  data() {
    return {
      searchText: '',



    }



  },
  computed: {
    allthestuff() {
      return this.movieResults;
    }

  },
  methods: {
    findResults() {
      console.log(this.searchText);
      let value = this.searchText;

      const url = "https://api.themoviedb.org/3/search/movie?api_key=6b33c7bf2d0169a646f34a5f0595b9f3&language=en-US&query=" + value + "&page=1&include_adult=false";
      console.log(url);

      fetch(url)
      .then(function(response) {
        return response.json();
      }).then(function(json) {
        console.log(json);
        console.log(json.results[0].title);
        console.log(json.results[0].overview);

        this.movieResults = json.results;

      });
    }

  },

}
</script>


