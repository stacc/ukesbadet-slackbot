# Slackbot

Dette vil beskrive hvordan man setter opp en Slackbot.

### Installasjon

Antar at slack-app er korrekt satt opp i https://api.slack.com/apps/

- Installer ngrok globalt `npm install ngrok -g`
- Lag en `.env` fil og legg inn app credentials

```
# .env
# Hent fra fanen "Basic Information"
SLACK_SIGNING_SECRET=<signing-secret>
# Hent fra fanen "OAuth & Permissions"
SLACK_BOT_TOKEN=<xoxb-...>
```

- `npm install`

### Handshake og kjøring av applikasjon

- `nodemon index.js`
- I annen terminal:
  `ngrok http 3000`
- Hent ut url (https) fra ngrok
- Gå til https://api.slack.com/apps/A041Q4DPDU4/general[https://api.slack.com/apps/A041Q4DPDU4/general]
- Event Subscriptions -> Enable Events -> paste inn ngrok ${url}/slack/events
- Request URL må bli verified her
