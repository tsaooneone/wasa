<template>
  <div>
    <select v-model="inputType">
      <option>text</option>
      <option>radio</option>
      <option>select</option>
    </select>
    <ChangeType :type = "inputType" />
  </div>
</template>

<script>
import ChangeType from '../components/ChangeType.vue'
export default {
  name: 'Work2View',
  data () {
    return {
      inputType: 'text'
    }
  },
  components: {
    ChangeType
  }
}
</script>
