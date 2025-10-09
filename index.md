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

        window.addEventListener("onEmbeddedMessagingButtonClicked", async () => {
          console.log("onEmbeddedMessagingButtonClicked event received");
          const user_detail = getDetails(); //Replace the method as per your codebase.
          //Set values for hidden fields used in Salesforce Embedded Messaging.
          //Important:
          // - Field API names are **case-sensitive** and must exactly match the configuration in Salesforce.
          // - Do **not** rename or modify existing parameter keys.
          // - If you need to include additional fields, ensure they are first configured in Salesforce before adding them here.
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
            Contact_ID: user_detail.contactId,
            Loan_ID: user_detail.loanId,
            Page_Info: user_detail.pageInfo,
            DPD: user_detail.dpd,
            Device_Type: user_detail.deviceType
          });
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
