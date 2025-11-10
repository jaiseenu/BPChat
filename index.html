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
        DPD: urlParams.get('dpd'),
        Session_ID: urlParams.get('sessionId')
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
        console.log("##embeddedservice_bootstrap:", embeddedservice_bootstrap);
        console.log("##embeddedservice_bootstrapsettings:", embeddedservice_bootstrap.settings);
        embeddedservice_bootstrap.settings.language = 'en_US';
        embeddedservice_bootstrap.settings.enableUserInputForConversationWithBot = true;


        window.addEventListener("onEmbeddedMessagingReady", () => {
           console.log("Received the onEmbeddedMessagingReady event.");

           // Send your identity token to Salesforce.
           embeddedservice_bootstrap.userVerificationAPI.setIdentityToken({
              identityTokenType: "JWT",
              identityToken: "eyJraWQiOiJCb3Jyb3dlclBvcnRhbFdlYkNoYXRLaWQiLCJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJCUFdlYkNoYXQiLCJzdWIiOiIwMDNjZTAwMDAwTmM4SXhBQUoiLCJleHAiOjE3NjE4MTA5MzgsImlhdCI6MTc2MTgwNzMzOH0.PPu2HRKFNVoDkWPoambGsasjwMq5OWrrTMjEMl5qe0yLkYSo6BtNVNojCHMb3YkjEjw-NPcmw2fpvuqaBjhpScLhc0476JIHIXuT9fg2y6gbm0BBdyiJASkSiPtljekb20ccLpK2dyXHUJHVEPHbuzIRcac0QnABbBMjc3D3P6AuzeajfeX1x8GJ_e6K-3OqAfeNKDy95F0d4BA-PfSOxT10UugPinPy8dGK-JxT9P2EmGA6OMELVgjpH_RxaK-onsBISidS3ym7JHURMQTqg6OCW2FitPyTG3ybsTwz0seUk3KNl3SVMY2R5U7MV2to_K2UlgPCnh0YuljR-9fguA",
            });
        });
        // When user manually clicks the chat button
        window.addEventListener("onEmbeddedMessagingButtonClicked", () => {
          console.log("onEmbeddedMessagingButtonClicked event received");
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
        });

        window.addEventListener("onEmbeddedMessagingButtonCreated", () => {
          console.log("onEmbeddedMessagingButtonCreated event received");
          console.log("##embeddedservice_bootstrapCREATE:", embeddedservice_bootstrap);
          console.log("##embeddedservice_bootstrapsettingsCREATE:", embeddedservice_bootstrap.settings);
        });

        // Initialize Embedded Messaging
       embeddedservice_bootstrap.init(
          '00Dce000001LoFm', // Org ID
          'Borrower_Portal', // Deployment name
          'https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660', // Site endpoint
          { scrt2URL: 'https://pflms--qa.sandbox.my.salesforce-scrt.com' } // SCRT URL
        );

      } catch (error) {
        console.error("Error initializing Embedded Messaging:", error);
      }
    }
  </script>

  <!-- Salesforce Embedded Messaging Bootstrap -->
  <script type='text/javascript' src='https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
</body>
</html>
