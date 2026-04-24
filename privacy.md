# ScanMole Privacy Policy

_Last updated: 2026-04-24_

This policy explains what ScanMole ("the app", "we") does with your data. ScanMole is operated by **Konstantinos Spyrikos** ("we", "us"). Contact: **scanmole.support@gmail.com**.

> ⚠️ This is a starting draft covering common ground, not legal advice. Have a qualified lawyer review it before scaling commercially in the EU or US.

## 1. What ScanMole is

ScanMole is a personal mole-tracking aid. It lets you photograph spots on your skin, receive an AI-generated description using the clinical ABCDE framework, and keep a private timeline of photos so you can notice changes over time. **ScanMole is not a medical device and does not provide medical diagnoses.**

## 2. What data we collect

### 2.1 Stored only on your device
- **Photos of your skin** you capture or upload within the app
- **AI-generated descriptions and labels** for each photo
- **Mole metadata** you add (custom names, body-part tags, dates)
- **App preferences** (language, notification toggle)

This data lives in your phone's local storage (AsyncStorage + the app's document directory). We never receive, upload, or see it unless you send it to the AI analyzer (see 2.2).

### 2.2 Sent to our server when you run a scan
- **The photo**, base64-encoded, sent via HTTPS
- **Body-part label** you selected (e.g., "arm")
- **Your language preference**
- **A randomly generated device ID** stored only in your app install, used to count your free scans and prevent abuse

Our server forwards the photo to **Anthropic** (see 3.1) and returns the AI's JSON response to your app. We do not store the photo on our server; we only record a counter of how many scans that device ID has used this month.

### 2.3 Automatically collected
- **IP address** at the moment of each request (standard HTTPS; Cloudflare may log it for abuse prevention for up to 24 hours).
- We do **not** use third-party analytics, ad networks, or tracking SDKs in v1.

## 3. Who we share data with

### 3.1 Anthropic (sub-processor)
Each scan's photo is sent to Anthropic's Claude API for image analysis. Anthropic's privacy practices are described at <https://www.anthropic.com/privacy>. Anthropic states it does not train on API inputs by default. We do not retain the photo after the response is returned.

### 3.2 Cloudflare (sub-processor)
Our server runs on Cloudflare Workers. Cloudflare handles HTTPS termination and rate limiting. See <https://www.cloudflare.com/privacypolicy/>.

### 3.3 No one else
We do not sell, rent, or share your data with advertisers, brokers, or third parties beyond the sub-processors above.

## 4. Your rights

- **Access and export** — all your mole data is on your device. You can export it at any time from Settings → Your Data (coming soon) or by uninstalling the app (which deletes everything).
- **Deletion** — Settings → Danger Zone → Clear All Data wipes the device. Our server-side usage counter auto-expires after ~40 days and contains no personal content.
- **EU/UK residents (GDPR)** — contact us at **scanmole.support@gmail.com** to exercise your rights (access, correction, deletion, portability, objection).
- **California residents (CCPA)** — same; we do not sell personal information.

## 5. Medical disclaimer

ScanMole is a **tracking aid, not a diagnostic tool**. The AI analysis is informational and may be wrong. It is not a substitute for examination by a qualified dermatologist. If you are concerned about any skin change, consult a licensed medical professional promptly.

## 6. Children

ScanMole is not directed to children under 16. We do not knowingly collect data from children. If you believe a child has used the app, contact us and we will delete any associated data.

## 7. Security

Photos in transit are encrypted with TLS. Photos at rest live only on your device, inside the app's sandbox (not shared with other apps or the photo library unless you choose to save them). We hold the Anthropic API key encrypted in Cloudflare's secret store.

No system is perfect. If you spot a security issue, please email **scanmole.support@gmail.com** — we appreciate responsible disclosure.

## 8. Changes to this policy

If we change how we handle data, we will update this document and bump the "Last updated" date. Material changes will be announced in-app.

## 9. Contact

Questions or requests: **scanmole.support@gmail.com**.

---

**Plain-English summary:** Your photos live on your phone. When you tap "Scan," we send the photo to our server and on to Anthropic's AI, get the result, and throw the photo away. We count your scans so you don't exceed the free tier. We do not sell anything, we do not track you, and we do not claim to diagnose anything.
