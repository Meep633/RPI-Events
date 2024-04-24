# Requirements

Node version 20.x.x (install at https://nodejs.org/en)

# Installation

1. Clone repo: `git clone https://github.com/Meep633/RPI-Events.git <folder-name>`
2. Install dependencies: `cd <folder-name>/RPI-Events` and `npm i`
3. Recreate Mongo database: 
- Go to https://www.mongodb.com/lp/cloud/atlas/try4 and create a new database called `RPI-Events`
- Create a `.env` file in `<folder-name>` and put in `MONGODB=<connection-string>/RPI-Events`
4. Recreate Firebase app: 
- Go to https://console.firebase.google.com/ and create a new project called `rpi-events`
- Add authentication to the project and add the Email/Password and Google sign-in methods
- Create `.firebaseConfig.js` in `<folder-name>/RPI-Events/src/FireBase/` and put in the project's config (Overview -> Settings -> Scroll down)

Ex:
```
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
...
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);
```
- Create a new service account (Overview -> Settings -> Service accounts -> Generate new private key), create `.serviceAccountKey.json` in `<folder-name>/RPI-Events`, and put the service account's private key in it

Ex:
```
{
  "type": ...,
  "project_id": ...,
  "private_key_id": ...,
  "private_key": ...,
  "client_email": ...,
  "client_id": ...,
  "auth_uri": ...,
  "token_uri": ...,
  "auth_provider_x509_cert_url": ...,
  "client_x509_cert_url": ...,
  "universe_domain": ...
}
```
- Copy the firebase service account string on the same page where you generated the service account (top of page, under "Firebase service account"). In `<folder-name>/.env`, add `FIREBASE_SERVICE_ACCOUNT=<firebase string>` under `MONGODB=<connection string>/RPI-Events`

Ex:
```
FIREBASE_SERVICE_ACCOUNT=firebase-adminsdk-...@project.iam.gserviceaccount.com
```
5. Build application: In `<folder-name>/RPI-Events`, run `npm run build`
6. Start application in same directory: `node --env-file=../.env server`. Go to http://localhost:3000
