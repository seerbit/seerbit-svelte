<p align="center">
<img width="200" valign="top" src="https://assets.seerbitapi.com/images/seerbit_logo_type.png" data-canonical-src="https://assets.seerbitapi.com/images/seerbit_logo_type.png" style="max-width:100%; ">
</p>
 
# Seerbit Svelte Package
 
Seerbit Svelte Package can be used to integrate the SeerBit payment gateway into your svelte application.
 
## Requirements
 
Register for a merchant account on [Seerbit Merchant Dashboard](https://dashboard.seerbitapi.com) to get started.
 
```
  Svelte application
  Node js
  NPM
```
 
 ## Instalation

```bash
npm install seerbit-svelte
```

## API Documentation

https://doc.seerbit.com

## Support

If you have any problems, questions or suggestions, create an issue here or send your inquiry to care@seerbit.com

## Implementation

You should already have your API keys. If not, go to [dashboard.seerbitapi.com](https://dashboard.seerbitapi.com). Login -> Settings menu -> API Keys menu -> Copy your public key

## Properties

| Property            | Type               | Required | Default            | Desc                                                                                                                                                                                                                                    |
| ------------------- | ------------------ | -------- | ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| currency            | `String`           | Optional | NGN                | The currency for the transaction e.g NGN                                                                                                                                                                                                |
| email               | `String`           | Required | None               | The email of the user to be charged                                                                                                                                                                                                     |
| description         | `String`           | Optional | None               | The transaction description which is optional                                                                                                                                                                                           |
| fullName            | `String`           | Optional | None               | The fullname of the user to be charged                                                                                                                                                                                                  |
| country             | `String`           | Optional | None               | Transaction country which can be optional                                                                                                                                                                                               |
| transRef            | `String`           | Required | None               | Set a unique transaction reference for every transaction                                                                                                                                                                                |
| amount              | `String`           | Required | None               | The transaction amount in kobo                                                                                                                                                                                                          |
| callbackUrl         | `String`           | Optional | None               | This is the redirect url when transaction is successful                                                                                                                                                                                 |
| publicKey           | `String`           | Required | None               | Your Public key or see above step to get yours                                                                                                                                                                                          |
| closeOnSuccess      | `bool`             | Optional | False              | Close checkout when trasaction is successful                                                                                                                                                                                            |
| closePrompt         | `bool`             | Optional | False              | Close the checkout page if transaction is not initiated                                                                                                                                                                                 |
| setAmountByCustomer | `bool`             | Optional | False              | Set to true if you want user to enter transaction amount                                                                                                                                                                                |
| pocketRef           | `String`           | Optional | None               | This is your pocket reference for vendors with pocket                                                                                                                                                                                   |
| vendorId            | `String`           | Optional | None               | This is the vendorId of your business using pocket                                                                                                                                                                                      |
| tokenize            | `bool`             | Optional | False              | Tokenize card                                                                                                                                                                                                                           |
| customization       | CustomizationModel | Optional | CustomizationModel | CustomizationMode( borderColor: "#000000", backgroundColor: "#004C64", buttonColor: "#0084A0", paymentMethod:[PayChannel.card, PayChannel.account, PayChannel.transfer, PayChannel.momo], confetti: false , logo: "logo_url or base64") |
| onSuccess           | `Method`           | Optional | None               | Callback method if transaction was successful                                                                                                                                                                                           |
| onCancel            | `Method`           | Optional | None               | Callback method if transaction was cancelled                                                                                                                                                                                            |

## Usage

```Svelte page

 <script>
  import Seerbit from "seerbit-svelte";
</script>

	<Seerbit   
		public_key="YOUR PUBLIC KEY"
		tranref={new Date().getTime()}
		full_name="John Doe"
		amount="145.00"
		email="test@emaildomain.com"
		currency="NGN"
		country="NG"
		mobile_no=""
		productId=""
		description=""
		planId=""
		vendorId=""
		pocketReference=""
		setAmountByCustomer={false}
		tokenize={false}
		customization={{
			payment_method: ["card", "account", "transfer", "ussd", "momo"],
			confetti: true,
			logo: "",
			theme: {
			border_color:'fff',
			background_color:'fff',
			button_color:'fff',
			}
		}}
		onSuccess={(response, closeModal) => {
			console.log(response);

      setTimeout(() => closeModal(), 3000)
		}}
		close={(close) => {
			console.log(close);
		}}
		buttonText="Make Payment"
		buttonStyle={{
			style: "padding-top: 40px; padding-bottom: 40px; width: 50%; border-radius: 20px; color: #fff; background-color: red; font-size: 10px",
		}}
/>

```

`onSuccess` you will recieve a Map containing the response from the payment request.
