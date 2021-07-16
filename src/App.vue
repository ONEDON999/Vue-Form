<template>
<h1>Application forms</h1>
 <SignupForm />
   <footer>
    <p id="title" class="footer-h1">Coded by Nii-Gyan Christian. Dedicate This To: <a
        href="https://web.facebook.com/winifred.nketiajunior" target="_blank">(MY lover-Portia)</a></p>
    <div class="my-links">
      <a href="https://github.com/ONEDON999" target="_blank" class="footer-link"
        title="My GitHub Account">
        Visit 1Don on<i class="fa fa-github fa-2x" aria-hidden="true"></i>
      </a>
      <a href="https://twitter.com/NIIGYANCHRISTI2" target="_blank" class="footer-link" title="My Twitter Account">
        Visit 1Don on<i class="fa fa-twitter fa-2x" aria-hidden="true"></i>
      </a>
    </div>
  </footer>
</template>

<script>

import SignupForm from './components/Signup.vue'
export default {
  name: 'App',
  components: {SignupForm}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}body{
  margin: 0;
  background: linear-gradient(to bottom, #33ccff 0%, #ff99cc 100%);
}
</style>
