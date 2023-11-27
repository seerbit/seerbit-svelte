<script>
  import CheckoutScript from './CheckoutScript.svelte';
</script>

<CheckoutScript
  public_key="SBTESTPUBK_t4G16GCA1O51AV0Va3PPretaisXubSw1"
  tranref={new Date().getTime()}
  currency="NGN"
  country="NG"
  amount="145.00"
  email="test@emaildomain.com"
  mobile_no=""
  productId=""
  description=""
  setAmountByCustomer={false}
  full_name="John Doe"
  tokenize={false}
  planId=""
  pocketReference=""
  vendorId=""
  callbackurl="http://yourdomain.com"
  buttonText="Make Payment"
  buttonCustomization={{
    paddingVertical: 40,
    paddingHorizontal: 40,
    width: 50,
    color: "#fff",
    backgroundColor: "#000",
    fontSize: 10,
    borderRadius:20
  }}
/>


