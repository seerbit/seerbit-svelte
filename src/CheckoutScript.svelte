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
  export let callbackurl;
  export let buttonText;
  export let buttonCustomization;


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
      callbackurl,
    },
    function callback(response, closeModal) {
      console.log(response);
    },
    function close(close) {
      console.log(close);
    });
  }
</script>

<svelte:head>
  <title>SeerBit Simple Checkout</title>
  <script src="https://checkout.seerbitapi.com/api/v2/seerbit.js"></script>
</svelte:head>

<body>
  <button 
  style="
      padding-top:{buttonCustomization.paddingVertical}px;
      padding-bottom: {buttonCustomization.paddingVertical}px;
      padding-left: {buttonCustomization.paddingHorizontal}px;
      padding-right: {buttonCustomization.paddingHorizontal}px;
      font-size: {buttonCustomization.fontSize}px;
      background-color: {buttonCustomization.backgroundColor};
      color:{buttonCustomization.color};
      width: {buttonCustomization.width}%;
      border-radius: {buttonCustomization.borderRadius}px;
      border: none;
      cursor: pointer;
      transition: background-color 0.3s ease;
  "
  on:click={paywithSeerbit}>{buttonText}</button>
</body>
