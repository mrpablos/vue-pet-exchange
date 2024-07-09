<template>
  <input
    min="0"
    type="number"
    @input="changeAmount($event.target.value)"
    placeholder="Введите число"
  />
  {{ setCryptoFirst }}
  {{ setCryptoSecond }}
  <br />
  <button
    @click="convert()"
    :disabled="setCryptoFirst == '' || setCryptoSecond == ''"
  >
    Конвертировать
  </button>
  <button @click="favourite()" class="favButton">В избранное</button>
</template>

<script>
export default {
  props: {
    changeAmount: {
      type: Function,
      required: true,
    },
    convert: {
      type: Function,
      required: true,
    },
    favourite: {
      type: Function,
      required: true,
    },
    setCryptoFirst: {
      type: String,
      required: true,
    },
    setCryptoSecond: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
input {
  outline: none;
  border-radius: 4px;
  border: 4px solid #1a032d;
  padding: 10px 15px;
  background: #fafafa;
  color: #333;
  width: 500px;
  position: relative;
  top: -50px;
  font-size: 1.2em;
}

button {
  position: relative;
  top: -20px;
  margin: auto;
  padding: 15px 20px;
  color: #fff;
  text-transform: uppercase;
  cursor: pointer;
  background: #1a032d;
  border: 0;
  border-radius: 3px;
}

button.favButton {
  margin-left: 20px;
}
</style>
