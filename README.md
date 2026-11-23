# Unread Email Summariser

Import [`Unread Email Summariser.json`](Unread%20Email%20Summariser.json) into n8n. The workflow starts manually, fetches up to five unread Gmail messages, asks an AI Agent to summarize the sender, subject, and preview in one line of no more than 20 words, combines the `output` values into one array, and sends a single digest email.

## Configure before running

1. In n8n, create and connect a Gmail OAuth2 credential to both Gmail nodes. Enable the Gmail API in Google Cloud, configure the OAuth consent screen and redirect URI, and grant the read/send access requested by n8n.
2. Create an OpenAI credential in n8n and connect it to the OpenAI Chat Model node. The selected model is `gpt-4o-mini`.
3. Replace `YOUR_GMAIL_ADDRESS_HERE` in the **Email summary** node with the address where you want the digest delivered.
4. Run the workflow manually. The Aggregate node turns the per-email outputs into one `output` list; the final Gmail node joins that list with blank lines and sends one message.

Credential references and API keys are intentionally omitted from the export. An n8n execution, screenshots, and a screen recording require access to your n8n and Gmail accounts and must be completed there.
