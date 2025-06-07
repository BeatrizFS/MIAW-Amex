<html>
  <body>
    <script>
      // Variáveis que podem ser preenchidas pelo backend
      var FIRST_NAME = 'Test';
      var LAST_NAME = 'User';
      var BIN_NUMBER = '123456789';

      // Aguarda o Embedded Messaging ficar pronto para configurar os campos
      window.addEventListener("onEmbeddedMessagingReady", function(e) {
        // Aqui definimos os campos do pre-chat
        embeddedservice_bootstrap.prechatAPI.setPrechatFieldValues({
          FirstName: FIRST_NAME,
          LastName: LAST_NAME,
	  X10_first_digits_of_the_Card: BIN_NUMBER
        });

        embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
          BrowserLanguage: "Test"
        });
      });

      function initEmbeddedMessaging() {
        try {
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
          console.error('Erro ao carregar Embedded Messaging:', err);
        }
      }


    </script>

    <script
      type="text/javascript"
      src="https://axaus-travel--uatt.sandbox.my.site.com/ESWAmexExternalWebsite1749245413118/assets/js/bootstrap.min.js"
      onload="initEmbeddedMessaging()">
    </script>
  </body>
</html>
