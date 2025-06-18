1. run `git clone https://github.com/CrypticMessenger/n8n-local-starter.git`

2. change directory to the cloned repository: `cd n8n-local-starter`

3. create a `.env` file with the following content:

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

4. Signup for a free ngrok account. [link](https://dashboard.ngrok.com/get-started/setup/macos)

5. follow the installation instructions to install ngrok on your system.
`brew install ngrok`

6. Run `ngrok config add-authtoken <YOUR_NGROK_AUTH_TOKEN>` to authenticate your ngrok account.

7. claim a static domain for your ngrok account. 

8. Update the `.env` file with the claimed ngrok domain, e.g. `N8N_EDITOR_BASE_URL=https://xyz-abc-uvw.ngrok-free.app/` and `WEBHOOK_URL=https://xyz-abc-uvw.ngrok-free.app/`.

9. `docker compose up -d` to start the n8n service.

10. `ngrok http --url=xyz-abc-uvw.ngrok-free.app 5678` to expose the n8n service via ngrok.

11. You will be able to access n8n at `https://xyz-abc-uvw.ngrok-free.app/`.

12. `docker compose down` to stop the n8n service.