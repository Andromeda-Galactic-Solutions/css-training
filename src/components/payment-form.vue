<template>
  <form>
    <h2>Payment Information</h2>
    
    <label>
      First Name
      <input type="text" maxlength="100" required>
    </label>

    <label>
      Last Name
      <input type="text" maxlength="100" required>
    </label>

    <label>
      Email
      <input type="email" maxlength="100" required>
    </label>

    <label>
      Card Type
      <select required>
        <option value="visa">Visa</option>
        <option value="mastercard">Mastercard</option>
        <option value="americanExpress">American Express</option>
      </select>
    </label>

    <label>
      Card Number
      <input type="number" maxlength="100" required>
    </label>

    <label>
      Expiration Date
      <input type="date" required>
    </label>

    <button type="submit">Pay Now</button>
  </form>
</template>

<style scoped lang="scss">
  @use '../assets/scss/theme.scss' as *;
  @use '../assets/scss/mixins.scss' as *;
  label {
    @extend .label;
    display: block;
    margin-bottom: 1rem;
  }
  input, select {
    box-sizing: border-box;
    padding: 1ex 1ch;
    border: solid 1px $border-color;
    border-radius: 4px;
    font-family: var(--typography);
    display: block;
    width: 100%;
    &:invalid {
      border-left: solid 5px darkred;
    }
  }
  button {
    display: block;
    width: 80%;
    margin: 0 auto;
  }
</style>

<script>
export default { name: 'PaymentForm'  }
</script>
