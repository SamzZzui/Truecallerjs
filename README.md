1. Install the truecallerjs package:

npm install truecallerjs

Or install globally for CLI use:

npm install -g truecallerjs






---

Obtain Your InstallationId

This unique identifier is required to make API calls using TruecallerJS.

Login to Truecaller via the CLI:

truecallerjs login

(If you get an error, try adding sudo on Linux or running as Administrator on Windows.)


Alternate (Android users):

Open the Truecaller app, go to Settings → Privacy Center → tap “Download my data”.

A .json file will be downloaded (e.g., 1234567890-99123456789.json).

Then login using:

truecallerjs login /path/to/1234567890-99123456789.json




Retrieve the InstallationId:

truecallerjs --installationid

Or print just the ID with:

truecallerjs -i -r





---

Example Usage in Node.js

Once you have the InstallationId, you can invoke the search functionality via code:

const truecallerjs = require('truecallerjs');

var searchData = {
  number: "[PHONE_NUMBER]",
  countryCode: "[COUNTRY_CODE]",
  installationId: "[INSTALLATION_ID]"
};

truecallerjs.searchNumber(searchData)
  .then(response => console.log(response));



You can also specify output format, e.g., "JSON", "XML", "YAML", "TEXT", or "HTML":

var searchData = {
  number: "9912345678",
  countryCode: "IN",
  installationId: "YOUR_ID_HERE",
  output: "JSON"
};




---

Summary: README.md Highlights

Step	Command / Action

1. Install package	npm install truecallerjs or npm install -g truecallerjs
2. Login	truecallerjs login (or with JSON from Android data export)
3. Get InstallationId	truecallerjs --installationid or truecallerjs -i -r
4. Use in code	Call .searchNumber() with { number, countryCode, installationId, output }



---