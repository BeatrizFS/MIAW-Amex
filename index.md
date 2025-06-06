<html>
	<body>
		<script type='text/javascript'>
			function initEmbeddedMessaging() {
				try {
					// Detecta automaticamente o idioma do navegador
					let browserLanguage = navigator.language || navigator.userLanguage || 'en-US';
					
					// Exibe o valor detectado no console
					console.log('Detected browser language:', browserLanguage);
					
					// Define o idioma para o Embedded Service
					embeddedservice_bootstrap.settings.language = browserLanguage;

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
