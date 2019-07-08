<template>
  <div class="home">
    <Hero
      title="Greatest Website on Earth"
      subtitle="Better than Chocolate Cake"
      size="is-fullheight"
      color="is-info"
    />
  </div>
</template>

<script>
import Hero from "@/components/Hero";
export default {
  name: "home",
  components: {
    Hero
  }
};
</script>
