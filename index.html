<!DOCTYPE html>
<html lang="en">

<head>
    <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
</head>

<body>
    <script type="text/javascript">
        //Test Method to get details from the URL
        function getDetails() {
          const urlParams = new URLSearchParams(window.location.search);
		  //Important:
          // - Field API names are **case-sensitive** and must exactly match the configuration in Salesforce.
          // - Do **not** rename or modify existing parameter keys.
          // - If you need to include additional fields, ensure they are first configured in Salesforce before adding them here.
          const data = {
            Loan_ID: urlParams.get('loanId'),
            Contact_ID: urlParams.get('contactId'),
            Page_Info: urlParams.get('pageInfo'),
            Device_Type: urlParams.get('deviceType'),
            DPD: urlParams.get('dpd')
          };
          console.log("data:", data);
          return data;
        }

		async function sendMessage(msg){
			 embeddedservice_bootstrap.utilAPI.sendTextMessage(msg);
      .then(() => {
        console.log("MESSAGE SUCCESS", msg);
      }).catch(() => {
        console.log("MESSAGE ERROR");
      }).finally(() => {
        console.log("MESSAGE FIN");
      });
		}
    
        async function initEmbeddedMessaging() {
          try {
            embeddedservice_bootstrap.settings.language = 'en_US';
    
            let chatTimer = setTimeout(() => {
				    //Set values for hidden fields used in Salesforce Embedded Messaging.
                    embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
      				embeddedservice_bootstrap.utilAPI.launchChat()
      				.then(function (success) {
        				console.log("LAUNCH SUCCESS", success);
      				})
      				.catch(function (error) {
        					console.log("LAUNCH error", error);
      				})
      				.finally(function () {
        					console.log("LAUNCH finally");
						sendMessage('Welcome!');
      				});
      			}, 10000);
    
            window.addEventListener("onEmbeddedMessagingButtonClicked", async () => {
              console.log("onEmbeddedMessagingButtonClicked event received");
              //Set values for hidden fields used in Salesforce Embedded Messaging.
              embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
            });
            
            // Initialize embedded messaging
            embeddedservice_bootstrap.init(
              '00Dce000001LoFm',
              'Borrower_Portal',
              'https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660',
              { scrt2URL: 'https://pflms--qa.sandbox.my.salesforce-scrt.com' }
            );
          } catch (error) {
            console.error("Error initializing Embedded Messaging:", error);
          }
        }
    </script>

    <script    src="https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660/assets/js/bootstrap.min.js"    onload="initEmbeddedMessaging()">
    </script>
</body>

</html>
