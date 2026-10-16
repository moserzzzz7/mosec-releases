# Privacy Policy of Mosec Pass

Mosec Pass is a password manager: an app for Windows, an optional sync between your devices and a browser
extension that fills in your logins. This policy covers all of them. Last change: October 2026.

## What stays where

- **On your PC, your passwords, logins, notes and 2FA keys are stored encrypted** with your master password
  (scrypt and AES-256-GCM).
- **Sync is optional and end-to-end encrypted.** When you turn it on, every item is encrypted on your device with
  a key that only your devices hold (AES-256-GCM) before it is sent to the sync server, which runs on Cloudflare
  Workers (mosec-sync.king-87f.workers.dev). The server stores only these encrypted records, your account
  number, and the SHA-256 of two tokens that prove your device to it. It never receives your master password,
  the key, or any item in readable form, and nobody running the server can read them.
- **Your account is a number, not a person.** There is no email address, no name and no phone number.

## What the browser extension does with data

- You sign in once with your account number and master password. From them the extension derives the login
  (PBKDF2) and fetches your encrypted items from the sync server, then decrypts them in the browser.
- The key and the decrypted items are kept only in the browser's memory for the extension (session storage),
  not on disk, and web pages cannot reach them. Closing the browser, locking Windows or the lock button ends
  that. Only your account number is remembered, so that unlocking again asks just for the password.
- When you click the Mosec symbol in a login field, the extension shows the logins saved for the site you are
  on. When you choose one, it types its username, password and current 2FA code into the fields of that page.
  Pages only ever get the login you chose, and only for their own site.
- The extension only reads from the sync server; it changes nothing there. It does not read the content of pages
  beyond finding login fields, does not track the sites you visit, and sends no data to us or to third parties.
  It contains no analytics and no advertising.

## Other connections of the app

- **Updates:** the app looks up whether a newer version exists on GitHub (github.com/moserzzzz7/mosec-releases).
  This request contains no personal data beyond what any web request carries, such as your IP address.
- **Leak check (only when you start it):** the app checks your passwords against known data leaks with the
  "Have I Been Pwned" service. Only the first 5 characters of each password's SHA-1 hash are sent, never a
  password or a full hash.
- **Sync server:** like any web server, Cloudflare sees the IP address of a request. The sync server keeps a
  shortened SHA-256 of it with each new account, only to limit how many accounts one address can open in a day.

## Deleting your data

In the app, Sync, "Delete Sync Account" removes the account and every record of it from the server at once.
What your devices hold stays on them.

## Contact

Gian Moser, through github.com/moserzzzz7/mosec-releases (issues).
