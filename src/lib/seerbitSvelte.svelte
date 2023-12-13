<script>
  export let public_key;
  export let tranref;
  export let currency;
  export let country;
  export let amount;
  export let email;
  export let mobile_no;
  export let productId;
  export let description;
  export let setAmountByCustomer;
  export let full_name;
  export let tokenize;
  export let planId;
  export let pocketReference;
  export let vendorId;
  export let customization;
  export let buttonText;
  export let buttonStyle
  export let onSuccess;
  export let close;

  function paywithSeerbit() {
    SeerbitPay({
      public_key,
      tranref,
      currency,
      country,
      amount,
      email,
      mobile_no,
      productId,
      description,
      setAmountByCustomer,
      full_name,
      tokenize,
      planId,
      pocketReference,
      vendorId,
      customization
    },
    onSuccess,
    close,
  )}
</script>

<svelte:head>
  <title>SeerBit Checkout</title>
  <script src="https://checkout.seerbitapi.com/api/v2/seerbit.js"></script>
</svelte:head>

<body>
  <button 
  class="btn-seerbit-checkout"
  {...buttonStyle}
  on:click={paywithSeerbit}>{buttonText}</button>
</body>

<style>
		.btn-seerbit-checkout{
		cursor: pointer;
    transition: background-color 0.3s ease;
	}
</style>
