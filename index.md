<html>
  <body>
	<script type='text/javascript'>
		function initEmbeddedMessaging() {
			try {
				embeddedservice_bootstrap.settings.language = 'en_US';


				window.addEventListener("onEmbeddedMessagingReady", e => {
					embeddedservice_bootstrap.prechatAPI.setVisiblePrechatField({
						"_firstName":{
							"value":"Test",
							"isEditableByEndUser": false
						},
						"_lastName":{
							"value":"User",
							"isEditableByEndUser": false
						},
						"_email":{
							"value":"test.user@test.com",
							"isEditableByEndUser": false
						},
						"Phone":{
							"value":"12344546767",
							"isEditableByEndUser": false
						},
						"Country_Of_Card":{
							"value":"Brazil",
							"isEditableByEndUser": false
						},
						"Bank_Name":{
							"value":"Visa",
							"isEditableByEndUser": false
						}						
						
					});

				});


				embeddedservice_bootstrap.init(
					'00DOx000002jjB7',
					'Amex_Enhanced',
					'https://axaus-travel--dev.sandbox.my.site.com/ESWAmexEnhanced1748954605477',
					{
						scrt2URL: 'https://axaus-travel--dev.sandbox.my.salesforce-scrt.com'
					}
				);
			} catch (err) {
				console.error('Error loading Embedded Messaging: ', err);
			}
		};
	</script>
	<script type='text/javascript' src='https://axaus-travel--dev.sandbox.my.site.com/ESWAmexEnhanced1748954605477/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
  </body>
</html>
