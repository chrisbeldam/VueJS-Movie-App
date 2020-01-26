<template>
  <div id="app">
    <header>
      <h1>Movie Search Vue App</h1>
    </header>
    <main>
      <Search />
    </main>
  </div>
</template>

<script>
import Search from './components/Search';
export default {
  name: 'app',
  components: {
    Search
  },
  data(){
    return {}
  },
}
</script>

<style>

* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}

body {
	font-family: 'montserrat', sans-serif;
	background-color: #223343;
}

header {
	padding: 50px 15px 0px;
}

header h1 {
	color: #FFF;
	font-size: 48px;
	font-weight: 500;
	text-align: center;
}

main {
	width: 100%;
	max-width: 960px;
	margin: 0 auto;
}

section {
	padding: 15px;
}

</style>
