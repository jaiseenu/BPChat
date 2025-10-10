<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
  <title>Embedded Messaging Chat</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
    }
    .chat-controls {
      margin-top: 20px;
      display: flex;
      gap: 10px;
      align-items: center;
    }
    input[type="text"] {
      flex: 1;
      padding: 8px 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
      font-size: 14px;
    }
    button {
      padding: 8px 14px;
      background-color: #0070d2;
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }
    button:hover {
      background-color: #005fb2;
    }
  </style>
</head>

<body>
  <h3>Salesforce Embedded Messaging Test</h3>

  <!-- Input and Send Button -->
  <div class="chat-controls">
    <input id="userMessage" type="text" placeholder="Type your message..." />
    <button onclick="handleSendMessage()">Send</button>
  </div>

  <script type="text/javascript">
    // Extract parameters from URL
    function getDetails() {
      const urlParams = new URLSearchParams(window.location.search);
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

    // Send message to chat
    async function sendMessage(msg) {
      if (!msg || msg.trim() === "") {
        console.warn("Message is empty, skipping send.");
        return;
      }
      if (!window.embeddedservice_bootstrap?.utilAPI?.sendTextMessage) {
        console.warn("sendTextMessage API not available yet.");
        return;
      }

      embeddedservice_bootstrap.utilAPI.sendTextMessage(msg)
        .then(() => console.log("MESSAGE SUCCESS:", msg))
        .catch((error) => console.error("MESSAGE ERROR:", error))
        .finally(() => console.log("MESSAGE FINISHED"));
    }

    // Handle Send Button Click
    function handleSendMessage() {
      const input = document.getElementById("userMessage");
      const message = input.value.trim();
      if (message) {
        sendMessage(message);
        input.value = ""; // Clear input after sending
      }
    }

    // Initialize Embedded Messaging
    async function initEmbeddedMessaging() {
      try {
        embeddedservice_bootstrap.settings.language = 'en_US';

        // Automatically open chat after 10 seconds
        setTimeout(() => {
          console.log("Launching chat automatically...");
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
          embeddedservice_bootstrap.utilAPI.launchChat()
            .then((success) => {
              console.log("LAUNCH SUCCESS:", success);
              sendMessage('Welcome!');
            })
            .catch((error) => console.error("LAUNCH ERROR:", error))
            .finally(() => console.log("LAUNCH FINISHED"));
        }, 10000);

        // When the chat button is manually clicked
        window.addEventListener("onEmbeddedMessagingButtonClicked", () => {
          console.log("onEmbeddedMessagingButtonClicked event received");
          embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields(getDetails());
        });

        // Initialize Salesforce Embedded Messaging
        embeddedservice_bootstrap.init(
          '00Dce000001LoFm', // Org ID
          'Borrower_Portal', // Deployment Name
          'https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660',
          { scrt2URL: 'https://pflms--qa.sandbox.my.salesforce-scrt.com' }
        );

      } catch (error) {
        console.error("Error initializing Embedded Messaging:", error);
      }
    }
  </script>

  <!-- Salesforce Bootstrap Script -->
  <script 
    src="https://pflms--qa.sandbox.my.site.com/ESWBorrowerPortal1759909412660/assets/js/bootstrap.min.js"
    onload="initEmbeddedMessaging()">
  </script>
</body>
</html>
