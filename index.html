<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
</head>
<body>
  <script type="text/javascript">
    function getDetails() {
      const urlParams = new URLSearchParams(window.location.search);
      const user_detail = {
        loanId: urlParams.get('loanId'),
        contactId: urlParams.get('contactId'),
        pageInfo: urlParams.get('pageInfo'),
        deviceType: urlParams.get('deviceType'),
        dpd: urlParams.get('dpd')
      };
      console.log("user_detail:", user_detail);
      return user_detail;
    }

    async function initEmbeddedMessaging() {
      try {
        embeddedservice_bootstrap.settings.language = 'en_US';

        // Wait for the embedded messaging to be ready
        window.addEventListener("onEmbeddedMessagingReady", async () => {
          console.log("onEmbeddedMessagingReady event received");
        });

        
        window.addEventListener("onEmbeddedMessagingButtonCreated", async () => {
          console.log("onEmbeddedMessagingButtonCreated event received");
        });

        window.addEventListener("onEmbeddedMessagingButtonClicked", async () => {
          console.log("onEmbeddedMessagingButtonClicked event received");
          const user_detail = getDetails();
          console.log("user_detailLL:", user_detail);
          console.log("user_detailLLcontactId:", user_detail.contactId);
          // Set hidden pre-chat fields based on URL params
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
            Contact_ID: user_detail.contactId,
            Loan_ID: user_detail.loanId,
            Page_Info: user_detail.pageInfo,
            DPD: user_detail.dpd,
            Device_Type: user_detail.deviceType
          });
        });

        window.addEventListener("onEmbeddedMessagingConversationStarted", async () => {
          console.log("onEmbeddedMessagingConversationStarted event received");
        });

        window.addEventListener("onEmbeddedMessagingPreChatLoaded", async () => {
          console.log("onEmbeddedMessagingPreChatLoaded event received");
        });

        window.addEventListener("onEmbeddedMessagingPreChatSubmitted", async () => {
          console.log("onEmbeddedMessagingPreChatSubmitted event received");
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

  <script
    src="https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660/assets/js/bootstrap.min.js"
    onload="initEmbeddedMessaging()">
  </script>
</body>
</html>
