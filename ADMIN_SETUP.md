# Secure Admin Setup

The frontend `ADMIN_UID` controls which account sees the Admin button.
For actual Firestore security, the admin account should also have the Firebase
custom claim:

admin: true

Set this with a trusted server / Firebase Admin SDK. Do NOT try to set this
claim from browser JavaScript.

For a one-admin store:
1. Create your personal Firebase Auth account.
2. Copy its UID.
3. Put it in `firebase-config.js` as ADMIN_UID.
4. Using a trusted Admin SDK environment, set `{admin:true}` on that user's custom claims.
5. Deploy firestore.rules.

Physical-device-only admin access cannot be guaranteed by ordinary browser
JavaScript. Use Firebase App Check and keep the admin account private.
