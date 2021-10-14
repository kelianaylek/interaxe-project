<template>
  <div class="about">

    <div v-if="this.displayCode">
      <p>{{ this.code }}</p>
      <br>
    </div>

  </div>
</template>

<script>


export default {
  props: ['displayCode', 'code'],
  data: function() {
  return {
      showCodeModal : this.displayCode
    };
  },
  name: 'Home',
  components: {

  },
  methods:{

  }
}
</script>