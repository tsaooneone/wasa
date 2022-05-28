<template>
    <div class="work">
        <h1>This is a work page</h1>
        <MoneyFormat msg="MoneyFormat"/>
    </div>
</template>

<style lang="scss">
    .work{
        height: 100vh;
    }

</style>

<script>
import MoneyFormat from '@/components/MoneyFormat.vue'
export default {
  name: 'WorkView',
  components: {
    MoneyFormat
  }
}
</script>
