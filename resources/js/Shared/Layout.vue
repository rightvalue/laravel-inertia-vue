<template>
  <main>
    <slot />
  </main>
</template>

<script>
  export default {
    props: {
      title: String,
    },
    watch: {
      title(title) {
        this.updatePageTitle(title)
      },
    },
    mounted() {
      this.updatePageTitle(this.title)
    },
    methods: {
      updatePageTitle(title) {
        document.title = title ? `${title} - ${this.$page.app.name}` : this.$page.app.name
      },
      // TODO - add methods to update SEO meta tags
    },
  }
</script>
