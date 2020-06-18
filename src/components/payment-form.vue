<template>
  <div>
    <!-- <div>Payment Form</div> -->
    <!-- <pre>
      <code>
      Need a form with the following fields:
      - First Name, required, max length 100
      - Last Name, required, max length 100
      - Email, required, max length 100
      - Drop down, required, with the following options:
        * Visa
        * Mastercard
        * American Express
      - Card Number, required, max length 100
      - Expiration date, required
      </code>
    </pre> -->

    <form>

      <!-- <label>
        <input id="test" value="one" name="test" type="radio" checked>
        Radio 1
      </label>
      <br>
      <label>
        <input id="test2" value="two" name="test" type="radio">
        Radio 2
      </label> -->

      <label>
        Hidden
        <input id="test" name="test" type="hidden">
      </label>

    </form>
  </div>
</template>

<style scoped lang="scss">
  form {
    padding: 25px;
  }
</style>

<script>
export default { name: 'PaymentForm'  }
</script>
