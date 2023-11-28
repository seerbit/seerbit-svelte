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
  payment_method= {["ussd"]}
  confetti = {true}
  logo= "https://images.unsplash.com/photo-1575936123452-b67c3203c357?q=80&w=4140&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
  buttonText="Make Payment"
  theme={{
    border_color:'fff',
    background_color:'fff',
    button_color:'fff',
  }}
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


