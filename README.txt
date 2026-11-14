ONLYTWO — PRIVATE ONE-TO-ONE CHAT STARTER

This is a small responsive website for exactly two approved email accounts. It uses Firebase Authentication and Cloud Firestore. It has no public sign-up page.

IMPORTANT
- It is not live until you configure Firebase and deploy it.
- Do not share your passwords or Firebase service-account/private keys.
- The Firebase Web App config in index.html is intended to be public client config; the Firestore security rules are what protect chat data.
- Use two distinct email accounts. Do not use the same account on both phones.

SETUP (phone or computer; computer is easier)
1. Open https://console.firebase.google.com/ and sign in with a Google account.
2. Create a project named OnlyTwo.
3. In Project Overview, add a Web App (</>) named OnlyTwo. Copy its Firebase config.
4. Open index.html in a text editor. Replace the firebaseConfig values near the top with the config copied from Firebase.
5. In Firebase Console > Authentication > Get started > Sign-in method, enable Email/Password.
6. In Authentication > Users, use Add user to create exactly two accounts: your email and the other person's email. Set strong, separate passwords and share the second password privately. Do not enable public account creation.
7. In Firestore Database > Create database, create the database.
8. Open the Rules tab. Replace the rules with the contents of firestore.rules. Replace YOUR_EMAIL@example.com and OTHER_PERSON@example.com with the exact two account emails. Publish the rules.
9. Deploy the folder to a static host such as https://vercel.com/ or Firebase Hosting. For Vercel, upload the project folder/repository as a static site; the entry file is index.html. Alternatively use Firebase Hosting and follow its hosting setup instructions.
10. Open the deployed HTTPS link on both phones and sign in with the two accounts.

TEST SECURITY
- Sign in from both approved accounts and send test messages.
- Try a third account: it should fail to read or send messages because Firestore rules deny it.
- Never use Firestore test mode for a real private chat. Keep the published rules above.

CURRENT LIMITATIONS
- This starter supports text messages only. Photo/video uploads, push notifications, read receipts, and online presence are not included.
- Messages are stored in Firestore. They are access-controlled, but this starter does not provide end-to-end encryption. Do not use it for highly sensitive information.
- The chat currently displays messages in ascending order and has no pagination or delete feature.
