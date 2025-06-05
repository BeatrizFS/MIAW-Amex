<html>
  <body>
	<script type='text/javascript'>
		function initEmbeddedMessaging() {
			try {
				embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'


				window.addEventListener("onEmbeddedMessagingReady", e => {
				
				
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
					"value": "jane@test.com" ,
					"isEditableByEndUser": true
					},
				"Phone": {
					"value": "12121212" ,
					"isEditableByEndUser": true
					},
				"Bin Number": {
					"value": "1111111111" ,
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
  </body>
</html>
