## Certbot
The project is adjusted to use of certbot.  
This command might come in handy:  
```
docker run --rm --name certbot -v "./cert/www:/var/www/certbot/:rw" -v "./cert/conf:/etc/letsencrypt/:rw" certbot/certbot certonly --webroot --webroot-path /var/www/certbot/ -d <DOMAIN NAME>
```
Replace `<DOMAIN NAME>` at the end with your domain name.

## Things to change
Change following files:
- `.env`:
    | What to change | Note |
    | --- | --- |
    | `ORIGIN=` | Insert final domain name |
    | `VAPID=` | Used for notifications. Currently broken. |
    | `SECRET=` | Used for encrypting sessions. |
- `./config/`:
    - `keys.json`:
        | What to change | Note |
        | --- | --- |
        | `publicKey` | Add your own VAPID keys |
        | `privateKey` | Add your own VAPID keys |
    - `options.json`:
        Change your desired modules by swapping between `true` and `false` next to their name.
    - `usettings.json`:
        Most things can be changed on the fly inside of the app. `menu` is not done yet.
- `./ipwa`:
    - `Dockerfile`:
        | Line | What to change | Note |
        | --- | --- | --- |
        | 7 | ``apiEndpoint: `http://localhost/api`,`` | Change url to backend endpoint |

    - `httpd.conf`:
        | Line | What to change | Note |
        | --- | --- | --- |
        | 233 | `ServerAdmin you@example.com` | Change to webmaster's email |
        | 242 | `ServerName www.example.com` | Change to final domain name |
        | 312 | `ServerName www.example.com` | See above |
        | 314 | `SSLCertificateFile /cert/live/<domain>/cert.pem` | Change `<domain>` to the domain name above |
        | 315 | `SSLCertificateKeyFile /cert/live/<domain>/privkey.pem` | Change `<domain>` to the domain name above |
        | 316 | `SSLCertificateChainFile /cert/live/<domain>/chain.pem` | Change `<domain>` to the domain name above |
    - (Optional) `src/assets/icons/*` - You can change the icons to your own 
