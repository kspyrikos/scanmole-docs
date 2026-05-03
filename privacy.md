# ScanMole Privacy Policy

_Last updated: 2026-04-25_

This policy explains what ScanMole ("the app", "we", "us") does with your data. ScanMole is operated by **Konstantinos Spyrikos**, sole proprietor based in Denmark. Contact: **scanmole.support@gmail.com**.

## 1. What ScanMole is

ScanMole is a personal mole-tracking aid. It lets you photograph spots on your skin, receive an AI-generated **visual description** using the clinical ABCDE framework, and keep a private timeline of photos so you can notice changes over time. **ScanMole is not a medical device. It does not provide medical diagnoses, screenings, or recommendations.** The AI output describes visual features only and is intended to help you decide what to discuss with a qualified dermatologist.

## 2. What data we collect

### 2.1 Stored only on your device
- **Photos of your skin** you capture or upload within the app (special-category data under GDPR Article 9)
- **AI-generated visual descriptions** for each photo
- **Mole metadata** you add (custom names, body-part tags, dates, your own notes)
- **App preferences** (language, notification toggle)

This data lives in your phone's local storage (AsyncStorage + the app's document directory). We never receive, upload, or see it unless you actively trigger an AI scan (see 2.2).

### 2.2 Sent to our server when you run a scan
- **The photo**, base64-encoded, sent via HTTPS
- **Body-part label** you selected (e.g., "right arm")
- **Your language preference**
- **A randomly generated device ID** stored only in your app install, used to count your free-tier scans and prevent abuse

Our server forwards the photo to **Anthropic** (see 3.1) and returns the AI's JSON response to your app. We do not store the photo on our server; we only record a counter of how many scans that device ID has used this month.

### 2.3 Subscription state (paid users only)
If you subscribe via Google Play, our server stores: device ID, subscription tier (monthly/quarterly/yearly), expiry date, and an opaque transaction token from Google. **No payment card data ever reaches us** — Google Play handles all payment processing.

### 2.4 Automatically collected
- **IP address** at the moment of each request (standard HTTPS; Cloudflare may log it for abuse prevention up to 24 hours).
- We do **not** use third-party analytics, ad networks, or tracking SDKs.

## 3. Sub-processors

### 3.1 Anthropic PBC (USA) — AI vision processing
Each scan's photo is sent to Anthropic's Claude API for visual analysis. Anthropic's privacy practices: <https://www.anthropic.com/privacy>. Anthropic states it does not train on API inputs by default. Photos are processed in memory and not retained by Anthropic for training.

### 3.2 Cloudflare, Inc. (USA / global edge) — Hosting
Our server runs on Cloudflare Workers. Cloudflare handles HTTPS termination, edge caching, and rate limiting. <https://www.cloudflare.com/privacypolicy/>.

### 3.3 Google LLC (USA / EU) — Distribution + payments
Google Play distributes the app and processes any subscription purchases. Google's privacy: <https://policies.google.com/privacy>.

### 3.4 Expo (USA) — Build/distribution platform
We use Expo Application Services to build the app binary. Expo does not receive end-user data at runtime.

### 3.5 International data transfers
Anthropic, Cloudflare, and Google are headquartered in the USA. We rely on the EU-US Data Privacy Framework adequacy decision (effective 10 July 2023) plus Standard Contractual Clauses where applicable for these transfers.

### 3.6 No other sharing
We do not sell, rent, or share your data with advertisers, brokers, or third parties beyond the sub-processors above.

## 4. Legal basis (GDPR Art. 6 + 9)

- **Photos of skin** — special-category health data under Art. 9. Legal basis: your **explicit consent** given by tapping "Take Close-up" / "Choose from Library" (Art. 9(2)(a)).
- **Device ID and usage counters** — necessary for the performance of the contract / legitimate interest in preventing abuse (Art. 6(1)(b) + (f)).
- **Subscription data** — necessary for the contract (Art. 6(1)(b)).

## 5. Data retention

- **Photos and AI responses on your device**: kept until you delete them or uninstall the app.
- **Server-side scan counter**: auto-expires after 40 days (Cloudflare KV TTL).
- **Server-side subscription record**: retained while the subscription is active + 30 days after expiry, then auto-deleted.
- **Logs (Cloudflare)**: 24 hours.
- **Photos on our server**: never persisted; in-memory only during a single request.

## 6. Your rights (GDPR)

- **Access and export** — all your mole data is on your device. You can export it at any time from Settings → Your Data → Export. Or uninstall the app to wipe everything.
- **Rectification** — you can edit notes, names, risk levels, and positions in the app at any time.
- **Erasure** ("right to be forgotten") — Settings → Danger Zone → Clear All Data wipes the device. Server-side counters/subscriptions auto-expire.
- **Portability** — Settings → Your Data → Export creates a JSON copy of your moles you can take elsewhere.
- **Objection / restriction** — uninstall the app or contact us.
- **Withdraw consent** — uninstall + clear app data via Android Settings.
- **Complaint** — you have the right to complain to a data protection authority. The lead supervisory authority is the **Danish Data Protection Agency (Datatilsynet)**: <https://www.datatilsynet.dk>. You may also complain to your local national authority (e.g. for Greek residents, the Hellenic Data Protection Authority at <https://www.dpa.gr>).

To exercise any right, email **scanmole.support@gmail.com**. We will respond within 30 days.

## 7. Medical disclaimer

ScanMole is a **personal tracking and visualization aid only**. The AI's "riskLevel" output is a visual-appearance category, not a medical risk assessment. ScanMole does **not** provide medical advice, diagnoses, or screenings. It is **not** a registered medical device under EU MDR (Regulation 2017/745). Always consult a licensed dermatologist for any concerning skin change.

## 8. Children

ScanMole is not directed to users under 16. We do not knowingly collect data from children under 16. (GDPR Article 8 sets the default age of consent for information-society services at 16; some EU member states lower it to 13-15 — we apply the conservative 16+ requirement uniformly.) If you believe a child has used the app, contact us and we will delete any associated data.

## 9. Security

Photos in transit are encrypted with TLS 1.2+. Photos at rest live only on your device, inside the app's sandbox (not shared with other apps or the photo library unless you choose to save them). The Anthropic API key is held encrypted in Cloudflare's secret store. The admin token gating subscription endpoints is similarly encrypted.

If you spot a security issue, please email **scanmole.support@gmail.com** — we appreciate responsible disclosure.

## 10. Changes to this policy

If we change how we handle data, we will update this document and bump the "Last updated" date. Material changes will be announced in-app at least 14 days before they take effect.

## 11. Contact

Konstantinos Spyrikos (Data Controller)
Email: **scanmole.support@gmail.com**
Country: Denmark

---

**Plain-English summary:** Your photos live on your phone. When you tap "Scan," we send the photo to our server and on to Anthropic's AI, get the result, and throw the photo away. We count your scans so you don't exceed your tier. We do not sell anything, we do not track you, we do not claim to diagnose anything, and you can delete everything by uninstalling.
