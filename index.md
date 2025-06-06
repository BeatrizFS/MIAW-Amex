<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'
		
			window.addEventListener("onEmbeddedMessagingReady", e => {
				// Campos visíveis no pré-chat
				embeddedservice_bootstrap.prechatAPI.setVisiblePrechatFields({
				"_firstName": {
					"value": "Jane",
					"isEditableByEndUser": true
				},
				"_lastName": {
					"value": "Test",
					"isEditableByEndUser": true
				}
				});

				// Campos invisíveis
				embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
				"X10_first_digits_of_the_Card": {
					"value": "1111111111"
				},
				"Country_Of_Card": {
					"value": "Brazil"
				},
				"Bank_Name": {
					"value": "Visa"
				},
				"_email": {
					"value": "jane@test.com",
					"isEditableByEndUser": true
				},
				"Phone": {
					"value": "12121212",
					"isEditableByEndUser": true
				}
				});
			});

			embeddedservice_bootstrap.init(
				'00DOx000002jjB7',
				'Amex_GitHub',
				'https://axaus-travel--dev.sandbox.my.site.com/ESWAmexGitHub1749126101477',
				{
					scrt2URL: 'https://axaus-travel--dev.sandbox.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://axaus-travel--dev.sandbox.my.site.com/ESWAmexGitHub1749126101477/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
