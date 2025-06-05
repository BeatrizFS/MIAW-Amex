<html>
  <body>
	<script type='text/javascript'>
		function initEmbeddedMessaging() {
			try {
				embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'


					window.addEventListener("onEmbeddedMessagingReady", e => {
					embeddedservice_bootstrap.prechatAPI.setVisiblePrechatField({
						"_firstName":{
							"value":"Test",
							"isEditableByEndUser": false
						},
						"_lastName":{
							"value":"User",
							"isEditableByEndUser": false
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
