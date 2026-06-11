# FlightMode AI Operations

This file records the deployment information needed to operate the iOS app backend and model host. Do not commit real passwords, API keys, private keys, `.env` files, VM database files, or shell history to GitHub, even when the repository is private.

## GitHub

- Repository: `khysam2022/flightmode-ai-ios`
- Visibility: private
- Default branch: `main`

## VM

- Public API/model host: `https://flightmode.35-229-212-230.sslip.io`
- Public API base URL: `https://flightmode.35-229-212-230.sslip.io/api`
- VM IP: `35.229.212.230`
- SSH target format: `<vm-user>@35.229.212.230`
- SSH command:

```bash
ssh <vm-user>@35.229.212.230
```

Store the VM password or SSH key passphrase in a password manager. If a team member needs access, share it through the password manager instead of GitHub.

## zsh Setup

Use zsh on the development machine and VM. Put local-only exports in `~/.zshrc` or `~/.zprofile`; do not commit those files.

Recommended local exports:

```zsh
export VM_HOST="<vm-user>@35.229.212.230"
export GMAIL_APP_PASSWORD="<google-app-password>"
export AVIATIONSTACK_API_KEY="<aviationstack-api-key>"
```

Reload after editing:

```bash
source ~/.zshrc
```

## Backend Environment

Create the backend environment from the checked-in template:

```bash
cd backend
cp .env.example .env
```

Then fill in the real values locally or on the VM:

- `GMAIL_APP_PASSWORD`: Google app password for `skyhkgapp@gmail.com`
- `AVIATIONSTACK_API_KEY`: Aviationstack API key
- `STORE`: `sqlite` on the VM/local machine, `firestore` on Cloud Run
- `DB_PATH`: SQLite file path when using `STORE=sqlite`

## Deploy Backend To VM

```bash
cd backend
export VM_HOST="<vm-user>@35.229.212.230"
export GMAIL_APP_PASSWORD="<google-app-password>"
./deploy-vm.sh
```

## Deploy Update Metadata

```bash
cd backend
export VM_HOST="<vm-user>@35.229.212.230"
./deploy-update.sh
```

## Model Hosting

The `.litertlm` files are several GB each and are intentionally not stored in Git. Host them on the VM or another HTTPS object host, then configure the app with `OFFLINE_AI_PACKAGE_URL` in `Info.plist`.

Current app defaults:

- Auth API: `https://flightmode.35-229-212-230.sslip.io/api`
- Privacy/terms site: `https://khysam2022.github.io/flightmode-ai-site/`

## Secret Checklist

Keep these outside Git:

- VM password
- SSH private keys and passphrases
- Google app password
- API keys
- Stripe secrets
- Klook or affiliate credentials
- `.env` files
- SQLite user database files
- zsh history
