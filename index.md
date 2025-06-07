<html>
  <body>
    <script>
      // Variáveis que podem ser preenchidas pelo backend
      var FIRST_NAME = 'Test';
      var LAST_NAME = 'User';
      var BIN_NUMBER = '123456789';

      // Aguarda o carregamento do Embedded Messaging
      window.addEventListener("onEmbeddedMessagingReady", function (e) {
        embeddedservice_bootstrap.prechatAPI.setVisiblePrechatFields({
          "_firstName": {
            "value": FIRST_NAME,
            "isEditableByEndUser": false
          },
          "_lastName": {
            "value": LAST_NAME,
            "isEditableByEndUser": false
          },
          "X10_first_digits_of_the_Card": {
            "value": "1234567890",
            "isEditableByEndUser": false
          }
        });

        embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
          "BrowserLanguage": {
            "value": "ESP"
          }
        });
      });

      function initEmbeddedMessaging() {
        try {
          let browserLanguage = navigator.language || navigator.userLanguage || 'en-US';
          console.log('Detected browser language:', browserLanguage);

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
