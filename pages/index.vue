<template lang="pug">
.index.bg-primary-200.w-screen.h-screen
  //- Vee Validate Tester
  //- ValidationObserver
    ValidationProvider(rules="required|email" v-slot="{ errors }")
      input.bg-green-200(v-model="user.email" type="email" name="email" placeholder="email")
      span {{ errors[0] }}
</template>

<script lang="ts">
import { defineComponent, reactive } from '@nuxtjs/composition-api';

const index = defineComponent({
  setup() {
    const user = reactive({
      email: '',
      password: '',
    });

    return {
      user,
    };
  },
});

export default index;
</script>

<style lang="scss">
.index {
  @apply container mx-auto;
}
</style>