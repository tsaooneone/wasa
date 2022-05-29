<template>
    <div class="out">
        <h3>{{ type }}</h3>
        <div v-if="type === 'text'">
            <label>Type = text</label> <input type="text">
        </div>
        <div v-else-if="type === 'radio'">
            <label>Type = radio</label> <input type="radio"> Boy <input type="radio"> Girl
        </div>
        <div v-else-if="type === 'select'">
            <label>Type = select</label> <select><option>Boy</option><option>Girl</option></select>
        </div>
    </div>
</template>

<style lang="scss">
    .out {
        margin: 30px auto;
        h3 {
            margin-bottom: 15px;
        }
    }
</style>
<script>
export default {
  name: 'ChangeType',
  props: {
    type: String
  }
}
</script>
