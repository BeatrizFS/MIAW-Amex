<html>
  <body>
    <script>
      var FIRST_NAME = "Amex";
      var LAST_NAME = "Test";
      var EMAIL = "amex@test.com";
      var PHONE = "987654312";

      var CLIENT_ID = "1a2b3c4d76";
      var COUNTRY_OF_CARD = "Brazil";
      var BANK_NAME = "VISA";
      
      var BIN_NUMBER = "2345678901";
      var BIN_NUMBER_MASKED = BIN_NUMBER.slice(0, -4) + "****";
      
      var IPAddress = "161.69.53.12";
 
      window.addEventListener("onEmbeddedMessagingReady", function (e) {
    
		const userAgent = navigator.userAgent;
		
		const fetchBrowserInfo = () => {
		  "UserAgent" : userAgent,
		  "ScreenResolution" : screenResolution,
		  "X10_first_digits_of_the_Card" : BIN_NUMBER,
          "IpAddress" : IPAddress
				
		});
	  });
 
      function initEmbeddedMessaging() {
        try {
            
            /*Using page parameters:
            //let browserLanguage = navigator.language || navigator.userLanguage || 'en-US';
            //console.log('First Information:', browserLanguage);
            //let supportedLanguages = ['en-US', 'es', 'pt-BR'];
            //let finalLanguage = supportedLanguages.includes(browserLanguage) ? browserLanguage : 'en-US';
            //console.log('Final language to use:', finalLanguage);
            //embeddedservice_bootstrap.settings.language = finalLanguage;*/

            //Using Variables:            
            var LANGUAGE = 'Spanish';
            var languageMap = {
            'Portuguese': 'pt-BR',
            'Spanish': 'es',
            'English': 'en-US'
            };
            var finalLanguage = languageMap[LANGUAGE] || 'en-US';
            embeddedservice_bootstrap.settings.language = finalLanguage;
            console.log('Defined language:', finalLanguage);

			embeddedservice_bootstrap.init(
				'00DHs000000PO0u',
				'Amex_External_Website',
				'https://axaus-travel.my.site.com/ESWAmexExternalWebsite1757341764203',
				{
					scrt2URL: 'https://axaus-travel.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
      }
    </script>
 
    <script
      type="text/javascript"
      src="https://axaus-travel.my.site.com/ESWAmexExternalWebsite1757341764203/assets/js/bootstrap.min.js"
      onload="initEmbeddedMessaging()">
    </script>
  </body>
</html>
