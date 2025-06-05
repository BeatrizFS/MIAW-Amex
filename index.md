<html>
  <body>
	<script type='text/javascript'>
		function initEmbeddedMessaging() {
			try {
				embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'


				window.addEventListener("onEmbeddedMessagingReady", e => {

					// Check if the method is available before using it

					if (embeddedservice_bootstrap.prechatAPI && embeddedservice_bootstrap.prechatAPI.setVisiblePrechatFields) {

						embeddedservice_bootstrap.prechatAPI.setVisiblePrechatFields({

							"_firstName": {

								"value": "Test",

								"isEditableByEndUser": true

							},

							"_lastName": {

								"value": "User",

								"isEditableByEndUser": true

							},

							"_email": {

								"value": "example@gmail.com",

								"isEditableByEndUser": true

							},

						});

						// Similarly, check for the presence of the method before using it

						if (embeddedservice_bootstrap.prechatAPI.unsetVisiblePrechatFields) {

							embeddedservice_bootstrap.prechatAPI.unsetVisiblePrechatFields(['_firstName','_lastName', '_email']);

						}

					} else {

						console.error("Embedded Service API methods not available.");

					}

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
  </body>
</html>
