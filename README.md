## Submodules
You need to pull the submodules
```
git submodule init
git submodule update
```

## Things to change
Change following files:
- `.env`:
    | What to change | Note |
    | --- | --- |
    | `DOMAIN=` | Insert final domain name |
    | `VAPID=` | Used for notifications. Currently broken. |
    | `EMAIL=` | Insert your email. Needed for SSL. |
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
    - (Optional) `src/assets/icons/*` - You can change the icons to your own 
