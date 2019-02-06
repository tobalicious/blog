<template>
  <div class="main-content columns is-marginless">
    <div class="column is-one-fifth is-paddingless">
      <SelectorCard
        v-for="option in options"
        @option-selected="test(option.index)"
      >
        {{option.name}}
      </SelectorCard>
    </div>

    <div
      class="column is-one-quarter is-paddingless test-outline"
    >
      <div v-if="selectedOption !== null">
        <SelectorCard
          v-for="article in options[selectedOption].articles"
          @option-selected="test2(article)"
        >
          {{article}}
        </SelectorCard>
      </div>

    </div>

    <div class="column is-paddingless test-outline">

    </div>

  </div>
</template>

<script>
import SelectorCard from '~/components/SelectorCard';

export default {
  name: 'HomePage',
  components: {
    SelectorCard
  },
  data() {
    return {
      options: [
        {
          name: 'Questions',
          index: 0,
          articles: ['q 1', 'q 2', 'q 3']
        },
        {
          name: 'Deep Dives',
          index: 1,
          articles: ['dd 1', 'dd 2', 'dd 3']
        },
        {
          name: 'Thoughts',
          index: 2,
          articles: ['t 1', 't 2', 't 3']
        },
        {
          name: 'Notes',
          index: 3,
          articles: ['n 1', 'n 2', 'n 3']
        }
      ],
      selectedOption: null
    }
  },
  methods: {
    test(index) {
      console.log(index);
      this.selectedOption = index;
    },
    test2(article) {
      console.log(article);
      //this.selectedOption = index;
    }
  }
}
</script>

<style lang="css" scoped>
.test-outline {
  border: 1px solid black;
}

.theme {
  font-size: 1.5em;
  width: 100%;
}


</style>
