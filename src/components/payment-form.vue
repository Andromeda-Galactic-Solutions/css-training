<template>
  <div class="payment-form">
    <h2>Payment Form</h2>
    <!-- <pre>
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
    </pre> -->
    <form>
      <div class="first-name">
        <label for="firstName">First Name</label>
          
          <input type="text"
            required
            maxlength="100"
            id="firstName"
            aria-errormessage="firstNameError"
            aria-invalid="true"
            v-on:blur="setInvalid('firstName')"
          />
          <p aria-live="polite" id="firstNameError" class="error">This field is required</p>
      </div>



      <div class="last-name">
        <label>
          Last Name
          <input type="text" required />
        </label>
      </div>
      <div class="email">
        <label for="email">Email</label>
        <input id="email" type="email" />
      </div>
      <!-- <div class="card-type">
        <label>Card Type</label>
        <select>
          <option aria-hidden="true" selected disabled>Please select a card type</option>
          <option value="v">Visa</option>
          <option value="m">Mastercard</option>
          <option value="a">American Express</option>
        </select>
      </div> -->
      <div class="radio card-type">
        <fieldset>
          <legend>Please select a card type</legend>
          <label><input name="card-type" type="radio">American Express</label>
          <label><input name="card-type" type="radio">MasterCard</label>
          <label><input name="card-type" type="radio">Visa</label>
        </fieldset>
      </div>
      <div class="card-number">
        <label>
          Card Number
          <input type="text" />
        </label>
      </div>
      <div class="expiration-date">
        <label>
          Experition Date
          <input type="month" />
        </label>
      </div>

      <button type="submit">Save me</button>
    </form>
  </div>
</template>

<style scoped lang="scss">
// theme
$primary: #6a5acd;
$primary-alt: #e6e2ff;

/* CSS Output */
section {
  color: #6a5acd;
  background: white;
  border: solid 1px lightgray;
  padding: 2ex 2ch;
}

.payment-form, textarea, input, datalist, select {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 1rem;
}
input, select {
  outline: none;
  outline: rgba(1, 1, 1, 0);
  border: solid 1px gainsboro;
  border-radius: 2px;
  padding: 2ex 2ch;
}
input:hover, 
select:hover {
  border: dotted 1px darkslateblue;
}
input:focus, 
select:focus {
  border: dashed 1px slateblue;
}
input:invalid {
  border-color: red;
}
fieldset {
  border-color: slateblue;
  border-width: 1px;
}
.error {
  color: red;
}
.error:before {
  content: 'ERROR: ';
  font-weight: bold;
}

// layout
.payment-form {
  padding: 1rem;
}
.payment-form div {
  margin-bottom: 1rem;
}
label,
input,
select,
text-area,
fieldset,
.error {
  box-sizing: border-box;
  display: block;
  width: 100%;
  max-width: 30ch;
  margin: 0 auto;
}
label {
  margin-bottom: .5ex;
}

.radio {
  input {
    display: inline-block;
    width: auto;
    margin-right: 1ch;
  }
}

.error { visibility: hidden; }
input:invalid ~ .error {
  visibility: visible;
}

.card {
  padding: 2ex 2ch;
  border: solid 1px lightgray;
  .card .title {
    color: slateblue;
    font-size: 1.25rem;
    font-weight: bold;
  }
}
</style>

<script>
  export default {
    name: "PaymentForm",
    methods: { setInvalid }
  };
  function setInvalid(id) {
    const elem = document.getElementById(id)
    if (!elem) { return }
    const isValid = elem.validity.valid
    elem.setAttribute('aria-invalid', !isValid)
  }
</script>
