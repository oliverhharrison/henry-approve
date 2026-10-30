# henry-approve

A tiny static page (`index.html`) used as a Telegram Mini App by a personal assistant bot, so that one person can confirm
approvals with Face ID on their own phone.

* It holds **no secrets** and no code from the assistant. The Face ID key is created on the phone and kept in Telegram's
  secure storage on the device.
* It makes **no network calls** other than loading `telegram-web-app.js` from `telegram.org`. No analytics.
* Mode comes from the URL fragment: `#enroll&n=<nonce>` or `#approve&c=<card id>&n=<nonce>`. Anything else shows "Nothing to do here."
* On approval the page sends a Telegram `sendData` message containing a one-time HMAC, never the key itself.

Served with GitHub Pages from the `main` branch root.
