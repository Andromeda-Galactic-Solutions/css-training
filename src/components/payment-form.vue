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
    <form v-on:submit="handleForm()">
      <div class="first-name">
        <label for="firstName">First Name</label>
          
          <input type="text"
            required
            name="firstName"
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
          <input type="text" required name="lastName" />
        </label>
      </div>
      <div class="email">
        <label for="email">Email</label>
        <input id="email" type="email" name="email" />
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
          <label><input name="card-type" value="amex" type="radio">American Express</label>
          <label><input name="card-type" value="mc" type="radio">MasterCard</label>
          <label><input name="card-type" value="visa" type="radio">Visa</label>
        </fieldset>
      </div>
      <div class="card-number">
        <label>
          Card Number
          <input type="text" name="cardNumber" />
        </label>
      </div>
      <div class="expiration-date">
        <label>
          Expiration Date
          <input type="month" name="expirationDate" />
        </label>
      </div>

      <button type="submit">Checkout</button>
    </form>
  </div>
</template>

<style scoped lang="scss">
// theme
@use '../assets/scss/theme' as t;
/* CSS Output */

.payment-form, textarea, input, datalist, select {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 1rem;
}
input, select {
  outline: none;
  outline: rgba(1, 1, 1, 0);
  border: t.$borders;
  border-radius: 2px;
  padding: 2ex 2ch;
}
input:hover, 
select:hover {
  border: dotted 1px t.$accent;
}
input:focus, 
select:focus {
  border: dashed 1px t.$primary;
}
input:invalid {
  border-color: t.$danger;
}
fieldset {
  border-color: t.$primary;
  border-width: 1px;
}
.error {
  color: t.$danger;
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
    methods: { setInvalid, handleForm }
  };
  function setInvalid(id) {
    const elem = document.getElementById(id)
    if (!elem) { return }
    const isValid = elem.validity.valid
    elem.setAttribute('aria-invalid', !isValid)
  }

  function handleForm() {
    const form = document.forms[0]
    console.log('form.submit', form)
    // alert(form.firstName.value)
  }
</script>
