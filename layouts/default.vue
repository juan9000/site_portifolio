<template>
  <div>
    <Header />
  </div>
</template>

<script>
import Header from '~/components/Header';

export default {
  components: {
    Header,
  },
  data () {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' }
        }
      ]
    }
  }
}
</script>
