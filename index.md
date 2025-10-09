<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
</head>
<body>
  <h3>Enter Device Type</h3>
  <input type="text" id="deviceTypeInput" placeholder="Enter device type (e.g. mobile/desktop)">
  <button id="submitDeviceType">Submit</button>

  <script type="text/javascript">
    // Function to read URL and input details
    function getDetails() {
      const urlParams = new URLSearchParams(window.location.search);
      const user_detail = {
        loanId: urlParams.get('loanId'),
        contactId: urlParams.get('contactId'),
        pageInfo: urlParams.get('pageInfo'),
        dpd: urlParams.get('dpd'),
        deviceType: document.getElementById("deviceTypeInput").value || urlParams.get('deviceType')
      };
      console.log("user_detail:", user_detail);
      return user_detail;
    }

    // ✅ Function to set hidden prechat fields
    function setHiddenPrechatFields() {
      const user_detail = getDetails();

      if (!embeddedservice_bootstrap?.prechatAPI) {
        console.error("Embedded Messaging not initialized yet.");
        alert("Chat widget not ready. Please try again later.");
        return;
      }

      console.log("Setting hidden prechat fields:", user_detail);

      embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
        Contact_ID: user_detail.contactId,
        Loan_ID: user_detail.loanId,
        Page_Info: user_detail.pageInfo,
        DPD: user_detail.dpd,
        Device_Type: user_detail.deviceType
      });

      alert("Device type and prechat fields set successfully!");
    }

    // Initialize Embedded Messaging
    async function initEmbeddedMessaging() {
      try {
        embeddedservice_bootstrap.settings.language = 'en_US';

        window.addEventListener("onEmbeddedMessagingReady", () => {
          console.log("onEmbeddedMessagingReady event received");
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

    // ✅ Button click event to trigger the function
    document.addEventListener("DOMContentLoaded", () => {
      document.getElementById("submitDeviceType").addEventListener("click", () => {
        const value = document.getElementById("deviceTypeInput").value.trim();
        if (!value) {
          alert("Please enter a device type before submitting.");
          return;
        }
        setHiddenPrechatFields();
      });
    });
  </script>

  <!-- Salesforce Embedded Messaging bootstrap -->
  <script
    src="https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660/assets/js/bootstrap.min.js"
    onload="initEmbeddedMessaging()">
  </script>
</body>
</html>
