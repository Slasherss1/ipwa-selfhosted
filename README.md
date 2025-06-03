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
    | `EMAIL=` | Insert your email. Needed for SSL. |
    | `SECRET=` | Used for encrypting sessions. |
