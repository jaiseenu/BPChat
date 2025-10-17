<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
  <title>Embedded Messaging</title>
</head>

<body>
  <script type="text/javascript">
    // Get details from the URL
    function getDetails() {
      const urlParams = new URLSearchParams(window.location.search);
      // Important:
      // - Field API names are case-sensitive and must exactly match the configuration in Salesforce.
      // - Do not rename or modify existing parameter keys.
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

    // Start the chat and set prechat fields
    async function startChat() {
      try {
        console.log("Starting chat...");
        embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
        const success = await embeddedservice_bootstrap.utilAPI.launchChat();
        console.log("LAUNCH SUCCESS:", success);
      } catch (error) {
        console.error("LAUNCH ERROR:", error);
      } finally {
        console.log("LAUNCH FINISHED");
      }
    }

    // Initialize Embedded Messaging
    async function initEmbeddedMessaging() {
      try {
        embeddedservice_bootstrap.settings.language = 'en_US';

        // When user manually clicks the chat button
        window.addEventListener("onEmbeddedMessagingButtonClicked", () => {
          console.log("onEmbeddedMessagingButtonClicked event received");
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
        });

        // Initialize Embedded Messaging
        let resp = embeddedservice_bootstrap.init(
          '00Dce000001LoFm', // Org ID
          'Borrower_Portal', // Deployment name
          'https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660', // Site endpoint
          { scrt2URL: 'https://pflms--qa.sandbox.my.salesforce-scrt.com' } // SCRT URL
        );
        console.log("resp::", resp);

      } catch (error) {
        console.error("Error initializing Embedded Messaging:", error);
      }
    }
  </script>

  <!-- Salesforce Embedded Messaging Bootstrap -->
  <script 
    src="https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660/assets/js/bootstrap.min.js"
    onload="initEmbeddedMessaging()">
  </script>
</body>
</html>
