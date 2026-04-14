# Microsoft Entra ID – Custom Domain Setup

## Why this matters

A custom domain (`@yourcompany.com`) replaces the default `onmicrosoft.com` for user sign-ins. This is required for brand consistency and is a core exam topic.

---

## Tools used

- Microsoft Entra ID (Azure portal)
- Hostinger (domain registrar – any registrar works)

---

## Steps

### 1. Add custom domain in Entra ID
- **Microsoft Entra ID** → **Domain names** → **Add custom domain**
- Enter your domain (e.g., `arizaylab.tech`)

### 2. Copy the TXT record from Azure
- Azure generates a value like `MS=ms16837434`
- Record type: `TXT`
- Host/Name: `@`
- TTL: `3600`

### 3. Add the TXT record at your registrar
- Log into your registrar (Hostinger, GoDaddy, etc.)
- Go to DNS settings → Add TXT record using the values from step 2
- Save

### 4. Wait for DNS propagation
- Takes 15–30 minutes (sometimes longer)

### 5. Verify in Azure
- Back in **Domain names** → Click **Verify**
- Status changes from *Unverified* to *Verified*

### 6. (Optional) Set as primary
- Click the verified domain → **Set as primary**
- New users get `user@yourdomain.com`

---

## Verification check

- [ ] Domain shows **Verified** in Entra ID
- [ ] Test user created with `@yourdomain.com` UPN
- [ ] User can sign in (if tested)

---

## Exam note

- Verification uses **TXT** or **MX** record
- DNS changes are not instant – propagation delay is normal
- Domain must be verified before setting as primary