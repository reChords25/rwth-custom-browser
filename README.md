# rwth-custom-browser
Provides custom scripts and / or configuration for RWTH Websites in modern browsers

## Tampermonkey Scripts
_Install Tampermonkey via your browser's official extension store. It has close to a million downloads, if not more, so don't choose the wrong one!_
For installing a new script, open the extension and click `Create new Script`. Then, replace the script's content fully with the corresponding `.js`-file's content from this repository.
### SSO-Auto-Login (`sso-auto-login.sh`)
This script can autofill your RWTH SSO login credentials each time you are redirected to the Single-Sign-On page. You don't even have to put in your 2FA code anymore - although it is planned to make this functionality optional, as it is somewhat unsafe in some usage scenarios.
After pasting and saving the script, you have to set the credentials store up once. Go to the Single-Sign-On page and open the extension. It will show an option: `Encrypt Credentials for This PC`. Click it and paste your username and password for SSO. Also, enter the "manual setup key" for a TOTP token. If you don't have a so-called secret for token generation because your main authentication method was set up another way (by scanning the QR code etc.), login to ITC self-service and create a new TOTP token and copy the manual setup key (many uppercase letters). Then also enter this key. You will be presented with a small pop-up window which shows a long string in the input field. Copy it and paste it inside the empty ticks at the begin of the script: `const ENCRYPTED_CREDS = '<paste here>'`. As soon as you save the script, you will be logged in automatically the next time you land on the SSO page.
