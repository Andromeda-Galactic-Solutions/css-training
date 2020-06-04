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

  </form>
</template>

<style scoped lang="scss"></style>

<script>
export default { name: 'PaymentForm'  }
</script>
