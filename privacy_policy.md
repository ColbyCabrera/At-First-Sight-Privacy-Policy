# Privacy Policy for At First Sight

**Effective Date:** August 13, 2026  
**Publisher:** LunaWorks (Colby Cabrera)  

Welcome to **At First Sight**, a sight-reading trainer mobile application. This Privacy Policy describes how we handle information in connection with your use of the At First Sight application on Android and iOS.

We are committed to protecting your privacy, providing an offline-first experience, and ensuring full transparency regarding data handling.

---

## 1. Privacy Philosophy & No Account Requirement

At First Sight is built with an offline-first design:
- **No User Accounts:** You are not required to create an account, log in, or register to use the application.
- **No Personal Identifiers:** We do not collect, request, or store personal identifiers such as your name, physical address, phone number, contact list, or advertising identifiers (`AD_ID`) on any external server.

---

## 2. Local Application Data (On-Device Storage)

To provide settings persistence and progress tracking, At First Sight saves specific application data locally on your device. This data is stored using native platform key-value storage mechanisms:
- **Android:** `SharedPreferences` (within `daily_limit_prefs`, `practice_stats_prefs`, `theme_prefs`, and `analytics_prefs`)
- **iOS:** `NSUserDefaults`
- **JVM/Desktop:** `java.util.prefs.Preferences`

The specific data stored locally includes:

### 2.1. Daily Generation Limit Data
Used to track and enforce daily sheet music generation limits for free-tier users.
- **Last Sheet Generation Date:** Timestamp string of the last generated sheet.
- **Sheets Generated Today:** Integer counter of sheets generated on the current day.

### 2.2. Practice Statistics
Used to record and display your sight-reading training progress and achievements.
- **Last Active Date:** Date string representing your last active practice session.
- **Streak Count:** Integer representing consecutive practice days.
- **Total Sheets:** Cumulative count of practice sheets generated.
- **Sum of Difficulties:** Integer used to compute average difficulty levels.
- **Recent Activities Log:** Serialized JSON list of recent practice records (sheet parameters and completion status).

### 2.3. App & Analytics Preferences
- **Theme Mode:** Chosen visual theme (System Default, Light Mode, or Dark Mode).
- **Analytics Collection Toggle:** Boolean flag recording your preference for enabling or disabling telemetry.

> **External Data Transfer Disclaimer:** None of the local settings, limits, or practice statistics listed above are transmitted to external servers. This data remains strictly sandboxed on your local device.

---

## 3. Permissions Requested & Purpose

At First Sight requests specific Android device permissions to operate:

### 3.1. Internet Access (`android.permission.INTERNET`)
Required for external network communication:
- **Sheet Music Rendering:** The app uses an embedded WebView to render sheet music. This WebView retrieves the open-source OpenSheetMusicDisplay JavaScript library from a public Content Delivery Network (CDN) (`https://cdn.jsdelivr.net/npm/opensheetmusicdisplay`) at runtime.
- **Subscription Verification:** Communicates with RevenueCat's secure servers (`api.revenuecat.com`) to check subscription status and verify entitlements.
- **Usage Telemetry:** Sends optional anonymized analytics events to Firebase Analytics (if enabled).

### 3.2. Network State & Wake Lock (`android.permission.ACCESS_NETWORK_STATE`, `android.permission.WAKE_LOCK`)
- **Network Check:** Used to verify network availability before attempting subscription or CDN requests to prevent unnecessary battery drain.
- **Background Dispatch:** Ensures system wake lock for brief background dispatching of analytics batches.

### 3.3. Vibration Controls (`android.permission.VIBRATE`)
- **Haptic Feedback:** Interacts with the device's haptic feedback engine (via `pulsar-kmp`) to provide subtle tactile responses when selecting difficulty levels, adjusting key signatures, or pressing UI controls.

---

## 4. Third-Party Services & Analytics

### 4.1. RevenueCat SDK (Subscriptions & In-App Purchases)
We integrate the RevenueCat SDK to manage in-app subscriptions for **At First Sight Pro**.
- **Data Transmitted:** Anonymized purchase tokens and transaction receipts.
- **Payment Processing:** All financial transactions, billing details, and credit card processing are handled securely by Google Play Store (Android) or Apple App Store (iOS). We never collect or store payment card details.

### 4.2. Firebase Analytics (Optional Telemetry)
On Android, we use Google Firebase Analytics to collect anonymized telemetry (e.g., screens viewed, practice sessions completed, feature usage).
- **No Advertising Tracking:** Advertising ID collection (`com.google.android.gms.permission.AD_ID`) is explicitly disabled in our manifest and build configuration.
- **Opt-Out Control:** Analytics collection is optional. You can turn telemetry on or off at any time in **App Settings**.

---

## 5. Children's Privacy

Because At First Sight does not collect or transmit personal identifiers or personal information, the application does not knowingly collect data from children under the age of 13. It is safe for musicians of all ages.

---

## 6. Data Retention & Deletion

All application data (practice statistics, streak counts, and local settings) is stored exclusively on your device. We do not host or back up this data on external servers.

You can permanently delete all local application data at any time by uninstalling the application or clearing the application data/cache in your device settings.

---

## 7. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. Any updates will be posted to our official documentation. Continued use of the application after an update constitutes acceptance of the modified policy.

---

## 8. Contact Information

If you have questions or feedback regarding this Privacy Policy, please contact us:

- **Publisher/Developer:** LunaWorks (Colby Cabrera)
- **Support Email:** [colbycabrera.wd@gmail.com](mailto:colbycabrera.wd@gmail.com)
- **Project Page:** [https://colbycabrera.github.io/sight-reading-trainer-app](https://colbycabrera.github.io/sight-reading-trainer-app)
- **Privacy Policy Repository:** [https://github.com/ColbyCabrera/At-First-Sight-Privacy-Policy](https://github.com/ColbyCabrera/At-First-Sight-Privacy-Policy)
