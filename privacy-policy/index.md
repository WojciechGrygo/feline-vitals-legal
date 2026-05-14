# Privacy Policy

**App:** Feline CKD Care  
**Effective Date: May 14, 2026**  
**Version: 1.0.0**

---

### The Short Version (TL;DR)

- **No Accounts Required.** You don't sign up. We don't know who you are.
- **Your Cat's Health Data Stays on Your Device.** All logs — weight, fluids, medications, lab results, symptoms — are stored in a private local database. They never reach our servers.
- **Analytics Are Opt-In.** Anonymous usage statistics (e.g. "weight was logged today") are only collected if you explicitly enable them in Settings. Disabled by default.
- **We Don't Sell Data.** We have no business model based on your data. We make money through Pro subscriptions only.

---

## 1. Who We Are

Feline CKD Care (the "App") is an independent mobile application for iOS and Android, built to help cat owners manage Chronic Kidney Disease (CKD). It is developed and maintained by:

**Wojciech Grygo**  
Email: **grygo.wojtek@gmail.com**

---

## 2. Information We Handle

### A. Data Stored Locally on Your Device

All health records you enter are saved exclusively to your device's internal storage using a SQLite database. This includes:

- Cat profiles (name, CKD stage, baseline weight)
- Daily logs: weight, subcutaneous fluid sessions (volume, site), medication doses, appetite, energy levels
- Litter box records and digestive symptoms
- Lab results (creatinine, BUN, phosphorus, SDMA, and up to 13 parameters)
- Feeding logs and food library
- Reminders and vet notes
- App settings (weight unit preference, analytics consent)

**We cannot access any of this data.** It is never transmitted to our servers.

**Backup:** Your data is included in your device's standard system backup:

- **iOS:** Backed up to iCloud automatically (if iCloud Backup is enabled).
- **Android:** Backed up to Google Drive automatically via Android Auto Backup.

You can verify backup status in your device's system settings (Profile → Data → tap to open settings).

---

### B. Anonymous Analytics (Opt-In Only)

If you choose to enable analytics in **Settings → Analytics**, the App sends anonymous, aggregate usage events to **Firebase Analytics** (Google). This data helps us understand which features are used most, so we can prioritize improvements.

**What we send (example events):**

- `weight_recorded` — a weight entry was saved
- `fluid_session_added` — a fluid session was logged
- `dmb_calculator_used` — the DMB calculator was opened
- `pdf_exported` — a PDF report was generated

**What we never send:**

- Actual values (weight numbers, fluid volumes, etc.)
- Cat names, vet notes, medication names, or any free-text content
- Lab result values
- Device identifiers beyond what Firebase generates automatically

Analytics collection is **disabled by default** in compliance with GDPR. You can change this at any time under **Settings → Analytics**.

---

### C. Crash Reporting

The App uses **Firebase Crashlytics** to automatically collect crash reports when the App unexpectedly closes. This helps us fix bugs faster.

Crash reports may include:

- The type of error and stack trace (technical code location)
- Device model and OS version
- App version

Crash reports do **not** include your cat's health data, vet notes, or any personal information you have entered.

---

### D. Subscription & Payments (Pro Features)

If you purchase the Pro subscription, the transaction is processed entirely by the **Apple App Store** or **Google Play Store**. We use **RevenueCat** to verify subscription status.

- We **never** see or store your payment card details.
- RevenueCat receives a pseudonymous subscriber ID and your subscription tier. It does not receive your health records.
- RevenueCat Privacy Policy: [https://www.revenuecat.com/privacy](https://www.revenuecat.com/privacy)

---

### E. Notifications

If you set up reminders (e.g., "Give fluids at 18:00"), the App uses **Expo / Apple Push Notification Service / Firebase Cloud Messaging** solely to deliver those local reminders to your device. No notification data is logged on our servers.

---

## 3. Trusted Partners

| Service                           | Purpose                                              | Privacy Policy                                           |
| :-------------------------------- | :--------------------------------------------------- | :------------------------------------------------------- |
| **Firebase Analytics** (Google)   | Anonymous feature usage statistics — **opt-in only** | [Google Privacy](https://policies.google.com/privacy)    |
| **Firebase Crashlytics** (Google) | Automatic crash reports for bug fixing               | [Google Privacy](https://policies.google.com/privacy)    |
| **RevenueCat**                    | Subscription status verification                     | [RevenueCat Privacy](https://www.revenuecat.com/privacy) |
| **Apple App Store**               | App distribution, payment processing (iOS)           | [Apple Privacy](https://www.apple.com/legal/privacy/)    |
| **Google Play Store**             | App distribution, payment processing (Android)       | [Google Privacy](https://policies.google.com/privacy)    |

---

## 4. Data Deletion

You are in full control of your data.

1. **Delete a cat profile:** Profile → Edit → Delete Profile. This removes all records associated with that cat.
2. **Uninstall the App:** Deleting the App from your device removes the local SQLite database. Note: data already backed up to iCloud or Google Drive may persist in those system backups according to their own retention policies.
3. **Disable Analytics:** Settings → Analytics → toggle off. Firebase will stop receiving new events immediately.
4. **Request deletion of analytics data:** Email us at **grygo.wojtek@gmail.com** and we will request deletion of any associated Firebase data under your device's pseudonymous ID.

---

## 5. Children's Privacy

Feline CKD Care is not directed at children under 13 (or under 16 in the European Economic Area). We do not knowingly collect personal information from children. If you believe a child has provided information, please contact us and we will remove it.

---

## 6. Global Compliance

### GDPR (European Union / EEA)

As a user from the EU/EEA, you have the following rights regarding any data Firebase may associate with your device:

- **Right to access** — request what data Firebase holds linked to your pseudonymous device ID.
- **Right to erasure** — request deletion of that data by emailing us.
- **Right to object** — disable analytics at any time in Settings.

The legal basis for analytics processing (when you opt in) is **explicit consent** (Art. 6(1)(a) GDPR). Crash reporting is processed under **legitimate interest** (App stability and bug fixing).

### CCPA (California)

We do not sell or share personal information with third parties for their own advertising or marketing purposes.

---

## 7. Changes to This Policy

If we materially change this Privacy Policy, we will update the Effective Date at the top and notify you via an in-app notice on the next launch. Continued use of the App after the notice constitutes acceptance.

---

## 8. Contact

Questions, requests, or concerns about privacy:

**Wojciech Grygo**  
Email: **grygo.wojtek@gmail.com**
