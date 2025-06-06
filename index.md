<html>
	<body>
		<script type='text/javascript'>
			function initEmbeddedMessaging() {
				try {
					embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

					embeddedservice_bootstrap.init(
						'00DOu000001GFQj',
						'Amex_External_Website',
						'https://axaus-travel--uatt.sandbox.my.site.com/ESWAmexExternalWebsite1749245413118',
						{
							scrt2URL: 'https://axaus-travel--uatt.sandbox.my.salesforce-scrt.com'
						}
					);
				} catch (err) {
					console.error('Error loading Embedded Messaging: ', err);
				}
			};
		</script>
		<script type='text/javascript' src='https://axaus-travel--uatt.sandbox.my.site.com/ESWAmexExternalWebsite1749245413118/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
	</body>
</html>
