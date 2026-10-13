# Privacy Policy of Mosec Pass

Mosec Pass is a password manager for Windows: an app on your PC and a browser extension that fills in what the
app holds. This policy covers both. Last change: October 2026.

## What stays where

- **Your passwords, logins, notes and 2FA keys are stored only on your PC**, encrypted with your master password
  (scrypt and AES-256-GCM). Nothing is sent to us or to any server we run. There is no account and no cloud.
- **The browser extension stores no passwords.** It keeps one thing in the browser's own storage: a random key
  that identifies your browser to the app after you allowed the connection once.

## What the browser extension does with data

- When you click the Mosec symbol in a login field, or open the extension's popup, the extension asks the Mosec
  Pass app **on the same PC** for the logins of the site you are on. To do so it passes the address of that page
  to the app, through the browser's native messaging, which never leaves your PC.
- The app answers only while it is running and unlocked, only to a browser you connected, and only with logins
  saved for that same site.
- When you choose a login, the app gives the extension its username, password and current 2FA code, and the
  extension types them into the fields of that page. Nothing else is done with them, and nothing is kept.
- The extension does not read the content of pages beyond finding login fields, does not track the sites you
  visit, and sends no data to us or to third parties. It contains no analytics and no advertising.

## Other connections of the app

- **Updates:** the app looks up whether a newer version exists on GitHub (github.com/moserzzzz7/mosec-releases).
  This request contains no personal data beyond what any web request carries, such as your IP address.
- **Leak check (only when you start it):** the app checks your passwords against known data leaks with the
  "Have I Been Pwned" service. Only the first 5 characters of each password's SHA-1 hash are sent, never a
  password or a full hash.

## Contact

Gian Moser, through github.com/moserzzzz7/mosec-releases (issues).
