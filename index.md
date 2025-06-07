<html>
  <body>
    <script>
      var FIRST_NAME = "Test";
      var LAST_NAME = "User";
      var EMAIL = "user@test.com";
      var PHONE = "987654321";

      var CLIENT_ID = "1a2b3c4d5e";
      var COUNTRY_OF_CARD = "Brazil";
      var BANK_NAME = "VISA";
	
	  var BIN_NUMBER = "123456789";
      var BIN_NUMBER_MASKED = BIN_NUMBER.slice(0, -4) + "****";	
	
      window.addEventListener("onEmbeddedMessagingReady", function (e) {

		const fetchBrowserInfo = () => {
			const ua = navigator.userAgent;
			let name = "Unknown";
			let version = "";

			if (ua.includes("OPR") || ua.includes("Opera")) {
				name = "Opera";
				version = ua.match(/OPR\/([\d.]+)/)?.[1] || ua.match(/Opera\/([\d.]+)/)?.[1];
			} else if (ua.includes("Edg")) {
				name = "Edge";
				version = ua.match(/Edg\/([\d.]+)/)?.[1];
			} else if (ua.includes("Chrome") && !ua.includes("Edg") && !ua.includes("OPR")) {
				name = "Chrome";
				version = ua.match(/Chrome\/([\d.]+)/)?.[1];
			} else if (ua.includes("Safari") && !ua.includes("Chrome")) {
				name = "Safari";
				version = ua.match(/Version\/([\d.]+)/)?.[1];
			} else if (ua.includes("Firefox")) {
				name = "Firefox";
				version = ua.match(/Firefox\/([\d.]+)/)?.[1];
			}

			return `${name} ${version}`;
		};

		const browserInfo = fetchBrowserInfo();
		const browserLanguage = navigator.language;
		const browserPlatform = navigator.platform;

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
            "value": BIN_NUMBER_MASKED,
            "isEditableByEndUser": false
          }
        });

        embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
		  "Email" : EMAIL,
		  "Phone" : PHONE,
		  "Client_Id" : CLIENT_ID,
		  "Country_Of_Card" : COUNTRY_OF_CARD,
		  "Bank_Name" : BANK_NAME,
		  "BrowserName" : browserInfo,
		  "BrowserLanguage" : browserLanguage,
		  "BrowserPlatform" : browserPlatform

        });
      });

      function initEmbeddedMessaging() {
        try {

			//let browserLanguage = navigator.language || navigator.userLanguage || 'en-US';
			//console.log('First Information:', browserLanguage);
			//let supportedLanguages = ['en-US', 'es', 'pt-BR'];
			//let finalLanguage = supportedLanguages.includes(browserLanguage) ? browserLanguage : 'en-US';
			//console.log('Final language to use:', finalLanguage);
			//embeddedservice_bootstrap.settings.language = finalLanguage;

			var LANGUAGE = 'Portuguese';
			var languageMap = {
			'Portuguese': 'pt-BR',
			'Spanish': 'es',
			'English': 'en-US'
			};
			var finalLanguage = languageMap[LANGUAGE] || 'en-US';
			embeddedservice_bootstrap.settings.language = finalLanguage;
			console.log('Idioma definido:', finalLanguage);			

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
