## Refer [medium blog](https://medium.com/@ankitsharma61016/get-started-with-n8n-100-free-100-locally-fa4c544b2f22) for more details.

----


````markdown
# 🛠 n8n Local Setup Guide (Docker + Ngrok)

Follow these step-by-step instructions to set up n8n **locally for free**.

---

## 1. Clone the Project Repo

```bash
git clone https://github.com/CrypticMessenger/n8n-local-starter.git
cd n8n-local-starter
````

> ⏱ Estimated time: <1 min

---

## 2. Install Docker

### For macOS:

```bash
brew install --cask docker
docker --version
```

> ⏱ Estimated time: \~3 min

---

## 3. Create a `.env` File

```bash
touch .env
```

> Ensure you're in the project root directory (`n8n-local-starter`) before running this.

---

## 4. Configure `.env` File

Paste the following inside `.env`:

```env
POSTGRES_USER=admin
POSTGRES_PASSWORD=adminpass
POSTGRES_DB=n8ndb
POSTGRES_NON_ROOT_USER=n8nuser
POSTGRES_NON_ROOT_PASSWORD=n8npass

# n8n Public URL and Settings
# Leave empty for now
N8N_EDITOR_BASE_URL=
WEBHOOK_URL=
N8N_COMMUNITY_PACKAGES_ALLOW=true
N8N_DEFAULT_BINARY_DATA_MODE=filesystem
```

---

## 5. Sign up on [ngrok](https://ngrok.com/) (Free Account)

> ⏱ Estimated time: \~2 min
> No payment info required

---

## 6. Install ngrok

```bash
brew install ngrok
```

> ⏱ Estimated time: \~2 min

---

## 7. Add Your ngrok Auth Token

```bash
ngrok config add-authtoken <YOUR_AUTH_TOKEN>
```

> Replace `<YOUR_AUTH_TOKEN>` with your actual token
> ⏱ Estimated time: <1 min

---

## 8. Claim a Free Static Domain on ngrok

Go to:
**Ngrok Dashboard → “Deploy Your App Online” → “Static Domain” → Claim**

---

## 9. Visit and Copy Your Static Domain

It will look like:
`https://your-chosen-subdomain.ngrok-free.app/`

---

## 10. Update `.env` with ngrok Domain

Edit `.env` again:

```env
N8N_EDITOR_BASE_URL=https://your-chosen-subdomain.ngrok-free.app/
WEBHOOK_URL=https://your-chosen-subdomain.ngrok-free.app/
```

---

## 11. Start the Containers

```bash
docker compose up -d
```

> This starts n8n and Postgres in the background
> ⏱ Estimated time: \~2 min

---

## 12. Expose Local Port via ngrok

```bash
ngrok http --domain=your-chosen-subdomain.ngrok-free.app 5678
```

> Your `5678` port should match the one in `docker-compose.yml`
> ⏱ Estimated time: <1 min

---

## 13. Access n8n via Browser

Go to:
`https://your-chosen-subdomain.ngrok-free.app/`

Signup only appears the **first time**.

---

## 14. Shut It Down (Optional)

```bash
docker compose down
```

> ⏱ Estimated time: <1 min

---

✅ That’s it! You now have **n8n running locally** with full control and zero cost.

Happy Automating! 🧠⚙️
