# Privacy Policy

**App:** FeliVitals  
**Effective Date:** September 17, 2026  
**Version:** 3.1.0

---

## The Short Version (TL;DR)

- **Accounts are optional.** You can use the App without creating an Apple or Google account. Signing in is required only for cloud backup, restore, and household sharing.
- **Most data stays on your device without an account.** Health records remain in the local database unless you choose to use the optional lab-report scanner. The selected report is then sent to Google Cloud for AI-assisted extraction.
- **AI scanning is optional.** FeliVitals does not permanently store the source photo or PDF. Extracted values are shown for your review and are saved only when you choose to save them.
- **Signed-in data syncs to the cloud.** When you sign in, your health records are stored in Firebase Firestore so they can be restored or shared.
- **Analytics and crash reporting are opt-in.** They are disabled until you enable them in Settings.
- **We do not sell your data.** FeliVitals is funded through Pro subscriptions, not the sale of personal information.

---

## 1. Who We Are

FeliVitals (the "App") is an independent mobile application for iOS and Android, built to help cat owners manage chronic health conditions, including Chronic Kidney Disease (CKD). It is developed and maintained by:

**Wojciech Grygo**  
Email: **grygo.wojtek@gmail.com**

---

## 2. Information We Handle

### A. Data Stored Locally on Your Device

Health records you enter are saved to your device's internal storage using a SQLite database. This includes:

- Cat profiles, such as name, CKD stage, and baseline weight
- Daily logs, including weight, fluids, medications, appetite, and energy
- Litter box records and digestive symptoms
- Lab results and supported laboratory parameters
- Feeding logs and food-library data
- Reminders and veterinary notes
- App settings, including unit preferences and privacy choices

If you do not sign in, these records are not synced to FeliVitals cloud storage. The optional lab-report scanner described in Section 2B is the exception: only a report you deliberately select for scanning is sent for processing.

Your local data may also be included in your device's system backup:

- **iOS:** iCloud Backup, if enabled on your device
- **Android:** Android backup, if enabled on your device

These backups are controlled by Apple or Google and are subject to their policies.

### B. Optional AI Lab-Report Scanning

When you select **Scan photo or PDF**, the App sends the selected veterinary laboratory report through an encrypted connection to a protected Firebase Cloud Function and then to **Google Cloud Vertex AI**. This can happen whether or not you have signed in with Apple or Google.

The scan is used only to extract supported laboratory fields into a structured draft. It does not provide a diagnosis, treatment recommendation, or medical advice.

The report may contain information visible in the document, including:

- Laboratory values, units, reference ranges, and report date
- Cat, owner, clinic, veterinarian, or patient identifiers printed on the report
- Other text or images included in the selected file

**How FeliVitals handles the report:**

- Source photos and PDFs are processed in memory and are not saved by FeliVitals to Firebase Firestore or Cloud Storage.
- Report contents, extracted values, prompts, and model responses are not written to Analytics, Crashlytics, or application logs.
- Extracted values are returned to your device for review.
- Extracted values become part of your health records only after you choose to save the form. If you are signed in, those saved values are then included in cloud sync as described in Section 2C.

**Technical and usage data:** To secure the service and enforce free and Pro limits, FeliVitals stores limited operational data. This may include a pseudonymous Firebase user ID, a hashed installation or subscription-owner identifier, scan status, timestamps, and usage counters. It does not include the source report or extracted laboratory values. Short-lived scan reservation records expire after processing and are removed by scheduled cleanup. Usage counters are retained while needed to enforce limits and prevent abuse.

**Google Cloud processing:** The Cloud Function runs in `us-central1`, and model processing uses Google's `us` multi-region. Google states that customer data is not used to train or fine-tune its AI models without the customer's permission or instruction. Under Google's standard abuse-monitoring rules, a prompt flagged by automated safety systems may be stored securely for up to 90 days in the selected region or multi-region and reviewed by authorised Google personnel. Such data is not used to train or fine-tune AI models. See [Google Cloud AI data retention](https://docs.cloud.google.com/gemini-enterprise-agent-platform/resources/zero-data-retention) and [Google Cloud abuse monitoring](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/abuse-monitoring).

### C. Cloud Account Data for Signed-In Users

When you sign in with Apple or Google, the App creates an account and syncs your health records to **Firebase Firestore**. This enables cloud backup, device restore, and household sharing.

Firebase Firestore may store:

- Your Firebase user ID (UID), a pseudonymous identifier generated by Firebase
- Email address and display name received from Apple or Google
- Household membership and roles
- Health records listed in Section 2A that are included in cloud sync
- Lab values that you reviewed and saved after an AI scan

Firebase Authentication may store:

- Your sign-in provider
- Your email address
- Authentication and refresh-token information needed to maintain or revoke access

**Household sharing:** If you join a shared household, other members can view and add records for cats in that household. The household owner controls membership and can remove members.

### D. Anonymous Analytics

If you enable analytics under **Settings → Analytics**, the App sends aggregate usage events to **Firebase Analytics**. Analytics is disabled by default.

Example events include:

- A weight entry was saved
- A fluid session was logged
- A calculator was opened
- A PDF report was generated

Analytics events do not contain cat names, notes, medication names, laboratory values, report files, diagnoses, or other health-record contents.

You can disable analytics at any time in Settings. Events collected before you disable analytics may remain according to Google's retention rules.

### E. Crash Reporting

If you give consent in the App, **Firebase Crashlytics** collects technical crash information, such as:

- Error type and stack trace
- Device model and operating-system version
- App version

Crash reporting is disabled before consent. Reports must not include health records, report files, extracted laboratory values, or free-text notes.

### F. Subscriptions and Payments

Purchases are processed by the **Apple App Store** or **Google Play Store**. FeliVitals uses **RevenueCat** to verify subscription status.

- FeliVitals does not receive or store payment-card details.
- RevenueCat receives a pseudonymous subscriber identifier, purchase history, and subscription status. For signed-in users, this information may be linked to their account.
- RevenueCat does not receive health records or lab-report files.
- On iOS, RevenueCat may also receive standard Apple Ads attribution data, such as campaign, ad-group, and keyword identifiers, to measure App Store advertising. FeliVitals does not use this data to track you across other companies' apps or websites.

See the [RevenueCat Privacy Policy](https://www.revenuecat.com/privacy).

### G. Notifications

If you create reminders, the App uses device notification services to deliver them. Notification data is not used for advertising and is not logged on FeliVitals servers.

### H. Security and App Attestation

FeliVitals uses **Firebase App Check**, Apple App Attest or DeviceCheck, and Google Play Integrity to help confirm that protected requests come from a genuine copy of the App. These services may process technical device, app, and attestation information. FeliVitals uses this information only for security and abuse prevention.

---

## 3. Trusted Service Providers

| Service | Purpose | Privacy information |
| :--- | :--- | :--- |
| **Firebase Firestore** (Google) | Optional cloud storage and OCR usage limits | [Google Privacy](https://policies.google.com/privacy) |
| **Firebase Authentication** (Google) | Signed-in accounts and pseudonymous authentication for protected services | [Google Privacy](https://policies.google.com/privacy) |
| **Firebase Cloud Functions** (Google) | Secure server-side processing for features including lab scanning | [Google Cloud Privacy](https://cloud.google.com/privacy) |
| **Vertex AI** (Google Cloud) | AI-assisted extraction from user-selected lab reports | [Google Cloud AI data retention](https://docs.cloud.google.com/gemini-enterprise-agent-platform/resources/zero-data-retention) |
| **Firebase App Check / Apple App Attest / Google Play Integrity** | App attestation, security, and abuse prevention | [Google Privacy](https://policies.google.com/privacy) |
| **Firebase Analytics** (Google) | Opt-in aggregate usage analytics | [Google Privacy](https://policies.google.com/privacy) |
| **Firebase Crashlytics** (Google) | Opt-in technical crash reports | [Google Privacy](https://policies.google.com/privacy) |
| **RevenueCat** | Subscription verification and standard Apple Ads attribution on iOS | [RevenueCat Privacy](https://www.revenuecat.com/privacy) |
| **Apple Sign In** | Authentication for Apple users | [Apple Privacy](https://www.apple.com/legal/privacy/) |
| **Google Sign In** | Authentication for Google users | [Google Privacy](https://policies.google.com/privacy) |
| **Apple App Store** | App distribution and iOS payment processing | [Apple Privacy](https://www.apple.com/legal/privacy/) |
| **Google Play Store** | App distribution and Android payment processing | [Google Privacy](https://policies.google.com/privacy) |

Google's processing of customer data is also governed by the [Google Cloud Data Processing Addendum](https://cloud.google.com/terms/data-processing-addendum).

---

## 4. Data Retention and Deletion

You can control or delete your data as follows:

1. **Delete a cat profile:** Use **Profile → Edit → Delete Profile**. This removes records associated with that cat locally and, if signed in, from cloud sync.
2. **Delete your account:** Use **Profile → Account → Delete Account**. This deletes your Firebase account and cloud health records managed by FeliVitals. Limited records that must be retained for security, subscription verification, fraud prevention, or legal obligations may remain for the required period.
3. **Delete local data:** Uninstalling the App removes its local database. Copies may remain in iCloud or Android system backups according to Apple or Google's retention rules. If you are signed in, uninstalling alone does not delete cloud data.
4. **Delete saved OCR results:** AI-extracted values are ordinary lab records after you save them. Delete the relevant lab record or cat profile to remove them.
5. **Source reports:** FeliVitals does not permanently store source photos or PDFs used for scanning, so there is no FeliVitals copy to delete after processing. Google may retain a report flagged by abuse-monitoring systems for up to 90 days as described in Section 2B.
6. **OCR usage data:** Pseudonymous quota and security records may remain after a scan to enforce limits and prevent abuse. You may request deletion by email, subject to records that must be retained for fraud prevention or legal obligations.
7. **Disable analytics and crash reporting:** Change your choice in Settings to stop future collection.
8. **Request assistance:** Email **grygo.wojtek@gmail.com** to request access, correction, deletion, or an export of data associated with your account.

---

## 5. Children's Privacy

FeliVitals is not directed at children under 13, or under 16 in the European Economic Area. We do not knowingly collect personal information from children. If you believe a child has provided personal information, contact us so we can review and remove it where required.

---

## 6. Legal Bases and Privacy Rights

### European Union and European Economic Area

Depending on the feature, FeliVitals relies on the following legal bases under the GDPR:

- **Local app functions and requested services, including cloud sync and AI lab scanning:** performance of a contract or steps taken at your request (Article 6(1)(b)).
- **Analytics and crash reporting:** consent (Article 6(1)(a)). You may withdraw consent in Settings.
- **Security, app attestation, rate limits, and fraud prevention:** legitimate interests in protecting users, the App, and its services (Article 6(1)(f)).
- **Records required by law:** compliance with a legal obligation (Article 6(1)(c)), where applicable.

You may have rights to access, correct, delete, restrict, object to processing, and receive a portable copy of your personal data. You may also withdraw consent and lodge a complaint with your local data-protection authority.

To exercise these rights, email **grygo.wojtek@gmail.com**. We may need to verify your identity before completing a request.

### International Transfers

Cloud processing may transfer data outside your country, including to the United States. The OCR Cloud Function runs in `us-central1`, and Vertex AI uses Google's `us` multi-region. Google states that international transfers are protected through its contractual and legal safeguards, including applicable Standard Contractual Clauses. See the [Google Cloud Data Processing Addendum](https://cloud.google.com/terms/data-processing-addendum).

### California

FeliVitals does not sell personal information or share it with third parties for their own cross-context behavioural advertising. California residents may contact us to request access, correction, or deletion where applicable.

---

## 7. Security

FeliVitals uses measures including encrypted network connections, Firebase security rules, authentication, app attestation, restricted service accounts, and access controls. No system is completely secure, but we work to reduce unauthorised access, disclosure, alteration, and loss.

---

## 8. Changes to This Policy

If we materially change this Privacy Policy, we will update the Effective Date and version above. Where required, we will also provide an in-app notice or request new consent.

---

## 9. Contact

Questions, requests, or concerns about privacy:

**Wojciech Grygo**  
Email: **grygo.wojtek@gmail.com**
