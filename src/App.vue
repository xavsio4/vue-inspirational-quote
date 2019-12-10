<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <inspirational-quote>
      <template v-slot:default="slotProps">
        <blockquote class="blockquote quote">
          &#8220;{{ slotProps.quote.body }}&#8221;
            <p>
              <em>&mdash;{{ slotProps.quote.author }}</em>
            </p>
        </blockquote>
      </template>
    </inspirational-quote>
  </div>
</template>

<script>
import InspirationalQuote from './components/InspirationalQuote.vue'

export default {
  name: 'app',
  components: {
    InspirationalQuote
  },
  data() {
    return {
    };
  }
}
</script>

<style>
.quote
{
  background-color:#eee;
  padding:6px;
}

</style>
