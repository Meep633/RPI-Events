# Requirements

Node version 20.x.x (install at https://nodejs.org/en)

# Installation

1. Clone repo: `git clone git@github.com:RPI-ITWS/itws4500-team11.git <folder-name>`
2. Install dependencies: `cd <folder-name>/RPI-Events` and `npm i`
3. Recreate Mongo database: Go to https://www.mongodb.com/lp/cloud/atlas/try4 and create a new database called `RPI-Events`
4. Create a .env file in `<folder-name>` and put in `MONGODB=<connection-string>/RPI-Events`
5. Build application: `cd RPI-Events` and `npm run build`
6. Start application in same directory: `node --env-file=../.env server`. Go to http://localhost:3000
