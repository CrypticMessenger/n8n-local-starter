1. create a `.env` file with the following content:

```plaintext
# fill in any values you wish to below
POSTGRES_USER= 
POSTGRES_PASSWORD=
POSTGRES_DB=
POSTGRES_NON_ROOT_USER=
POSTGRES_NON_ROOT_PASSWORD=

# n8n Public URL and Settings
# Replace YOUR_NGROK_DOMAIN.ngrok-free.app with the static domain you claim from ngrok
# Ensure it starts with https://
N8N_EDITOR_BASE_URL=
WEBHOOK_URL=
N8N_COMMUNITY_PACKAGES_ALLOW=true
N8N_DEFAULT_BINARY_DATA_MODE=filesystem
```

2. Signup for a free ngrok account. [link](https://dashboard.ngrok.com/get-started/setup/macos)

3. follow the installation instructions to install ngrok on your system.
`brew install ngrok`

4. Run `ngrok config add-authtoken <YOUR_NGROK_AUTH_TOKEN>` to authenticate your ngrok account.

4. claim a static domain for your ngrok account. 

5. Update the `.env` file with the claimed ngrok domain, e.g. `N8N_EDITOR_BASE_URL=https://xyz-abc-uvw.ngrok-free.app/` and `WEBHOOK_URL=https://xyz-abc-uvw.ngrok-free.app/`.

5. `docker compose up -d` to start the n8n service.

6. `ngrok http --url=xyz-abc-uvw.ngrok-free.app 5678` to expose the n8n service via ngrok.

7. You will be able to access n8n at `https://xyz-abc-uvw.ngrok-free.app/`.

8. `docker compose down` to stop the n8n service.