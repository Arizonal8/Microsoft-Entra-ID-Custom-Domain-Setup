# Microsoft Entra ID – Custom Domain Setup

## Purpose

A custom domain (`@arizaylab.tech`) was configured for a Microsoft Entra ID tenant to replace the default `onmicrosoft.com` domain for user sign-ins.

## Tools used

- Microsoft Entra ID (Azure portal)
- Hostinger (domain registrar)

## Steps completed

### 1. Domain purchase
The domain `arizaylab.tech` was purchased from Hostinger.

### 2. Domain added to Entra ID
Navigated to **Microsoft Entra ID** → **Domain names** → **Add custom domain**. Entered `arizaylab.tech`.

### 3. Verification record generated
Azure provided the following TXT record details:
- Type: `TXT`
- Name/Host: `@`
- Value: `MS=ms16837434`
- TTL: `3600`

### 4. TXT record added at registrar
Logged into Hostinger, opened the DNS Zone Editor for `arizaylab.tech`, and added a TXT record with the exact values above.

### 5. DNS propagation wait
Approximately 30 minutes were allowed for the DNS change to propagate.

### 6. Domain verified in Azure
Returned to **Domain names** in Entra ID and clicked **Verify** for `arizaylab.tech`. Status changed from *Unverified* to *Verified*.

### 7. Primary domain set (optional)
Clicked on the verified domain and selected **Set as primary**. New users now receive usernames ending with `@arizaylab.tech`.

### 8. Test user created
A test user named `User1` was created with the user principal name `User1@arizaylab.tech` to confirm functionality.

## Verification results

- Custom domain shows **Verified** in Entra ID.
- Users can be created with the custom domain.
- Tenant now supports branded sign-ins.
