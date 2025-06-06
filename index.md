<html>
  <body>
	<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US';

			window.addEventListener("onEmbeddedMessagingReady", e => {
				// Visíveis no pré-chat
				embeddedservice_bootstrap.prechatAPI.setVisiblePrechatFields({
					"_firstName": {
						"value": "Jane",
						"isEditableByEndUser": true
					},
					"_lastName": {
						"value": "Test",
						"isEditableByEndUser": true
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

				// Campos ocultos
				embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
					"X10_first_digits_of_the_Card": {
						"value": "1111111111"
					},
					"Country_Of_Card": {
						"value": "Brazil"
					},
					"Bank_Name": {
						"value": "Visa"
					}
				});
			});

			// Inicializa o canal
			embeddedservice_bootstrap.init(
				'00DOx000002jjB7', // ID da Org
				'Amex_GitHub', // Nome do Canal
				'https://axaus-travel--dev.sandbox.my.site.com/ESWAmexGitHub1749126101477', // URL do Deployment
				{
					scrt2URL: 'https://axaus-travel--dev.sandbox.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
	</script>

	<!-- Este script é essencial -->
	<script type='text/javascript' 
		src='https://axaus-travel--dev.sandbox.my.site.com/ESWAmexGitHub1749126101477/assets/js/bootstrap.min.js' 
		onload='initEmbeddedMessaging()'>
	</script>
  </body>
</html>
