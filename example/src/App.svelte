<script>
	export let name;
	import Seerbit from "seerbit-svelte";
</script>

<main>
	<h1>Hello {name}!</h1>

	<Seerbit   
		public_key="YOUR PUBLIC KEY"
		tranref={new Date().getTime()}
		full_name="John Doe"
		amount="145.00"
		email="test@mailinator.com"
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
</main>

<style>

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>