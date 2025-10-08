<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
</head>
<body>
  <script type="text/javascript">
  

    async function initEmbeddedMessaging() {
      try {
        const urlParams = new URLSearchParams(window.location.search);
        const loanId = urlParams.get('loanId');
        const contactId = urlParams.get('contactId');
        const pageInfo = urlParams.get('pageInfo');
        const deviceType = urlParams.get('deviceType');
        const dpd = urlParams.get('dpd');

        console.log("URL Params:", { loanId, contactId, pageInfo, deviceType, dpd });

        embeddedservice_bootstrap.settings.language = 'en_US';

        window.addEventListener("onEmbeddedMessagingReady", () => {
          console.log("onEmbeddedMessagingReady event received");

          // NOTE: The following field names (e.g., IP_Address, Referring_Site, etc.) 
          // must not be changed during assignment. These names must match 
          // exactly what is configured in Salesforce pre-chat mapping.
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
            Contact_ID: contactId,
            Loan_ID: loanId,
            Page_Info: pageInfo,
            DPD: dpd,
            Device_Type: deviceType
          });
        });

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
