# Privacy Policy

**Effective Date:** June 28, 2026

Welcome to **At First Sight**, a sight-reading trainer application. This Privacy Policy describes how we handle information in connection with your use of the At First Sight mobile application. 

This application is published by **LunaWorks (Colby Cabrera)** ("we", "us", or "our"). We are committed to protecting your privacy and ensuring a transparent user experience.

---

## 1. No Personal Information Collection

At First Sight is designed with an offline-first approach. 
* **No User Accounts:** You are not required to create an account, log in, or register to use the application.
* **No Personal Identifiers:** We do not collect, request, or store personal identifiers such as your name, email address, physical address, phone number, or device identifiers (like IMEI or advertising IDs) on any external server.

---

## 2. Local Application Data (Local Storage)

To provide you with settings persistence and progress tracking, At First Sight saves specific application data locally on your device. This data is stored using native platform key-value storage mechanisms:
* **Android:** `SharedPreferences` (specifically within `"daily_limit_prefs"`, `"practice_stats_prefs"`, and `"theme_prefs"`)
* **iOS:** `NSUserDefaults`
* **JVM/Desktop:** `java.util.prefs.Preferences`

The specific fields stored locally on your device include:

### 2.1. Daily Generation Limit Data
Used to track and enforce the daily limit on sheet music generations for free-tier users.
* **Last Sheet Generation Date:** A timestamp string representing the day of the last generated sheet.
* **Sheets Generated Today:** An integer counter tracking the quantity of sheets generated on the current day.

### 2.2. Practice Statistics
Used to record and present your training progress, achievements, and statistics.
* **Last Active Date:** A date string representing your last active practice session.
* **Streak Count:** An integer representing your consecutive days of practice.
* **Total Sheets:** The cumulative count of practice sheets generated.
* **Sum of Difficulties:** An integer used to compute average difficulty levels.
* **Recent Activities Log:** A serialized JSON string containing a list of your recent practice records (e.g., sheet parameters and completion status).

### 2.3. Theme Settings
Used to retain your visual application preferences.
* **Theme Mode:** A string indicating your chosen app theme (System Default, Light Mode, or Dark Mode).

**External Data Transfer Disclaimer:** None of the local settings, limits, or practice statistics listed above are transmitted to external servers. This data remains strictly sandboxed on your local device.

---

## 3. Permissions Requested and Their Purpose

At First Sight requires specific device permissions to operate. Below are details of the permissions declared in our application manifest and how they are used:

### 3.1. Internet Access (`android.permission.INTERNET`)
Required to enable external network communication for the following functions:
* **Sheet Music Rendering:** The app uses an embedded WebView to render sheet music. This WebView retrieves the open-source **OpenSheetMusicDisplay** JavaScript library dynamically from a public Content Delivery Network (CDN) (`https://cdn.jsdelivr.net/npm/opensheetmusicdisplay`) at runtime. Internet access is required to download this library so that the sheet music can be rendered visually on screen.
* **Subscription and Billing Verification:** The app integrates the RevenueCat SDK, which communicates with RevenueCat's secure servers (`api.revenuecat.com`) to check subscription statuses, process purchases, and verify entitlements.

### 3.2. Vibration Controls (`android.permission.VIBRATE`)
Required to interact with the device's haptic feedback engine:
* **Haptic Feedback:** The application utilizes Software Mansion's `pulsar-kmp` library to invoke subtle vibration patterns. This provides sensory haptic feedback when you interact with certain UI controls, such as selecting difficulty levels, adjusting time signatures, choosing key signatures, or interacting with toolbars.

---

## 4. Third-Party Services and SDKs

To facilitate premium features and purchases, At First Sight integrates third-party SDKs:

### 4.1. RevenueCat KMP SDK
We use the RevenueCat SDK to manage in-app subscriptions and purchases for the premium tier **"At First Sight Pro"**.
* **Data Transmitted:** The RevenueCat SDK handles transaction processing, subscription verification, and billing receipts. 
* **Payment Processing:** All financial transactions, billing details, and credit card processing are handled securely by the respective app stores (Google Play Store for Android or Apple App Store for iOS). We do not collect, store, or have access to your payment card details or financial information.
* **Privacy Policy:** RevenueCat processes transaction data in compliance with their privacy guidelines. You may review their policy on the RevenueCat official website.

---

## 5. Children's Privacy

Because At First Sight does not collect, request, or transmit any personal information or identifiers, the application does not knowingly collect any data from children under the age of 13. It is safe for musicians of all ages.

---

## 6. Data Retention and Deletion

All application data (practice statistics, streak counts, and settings) is stored exclusively on your device.
* We do not host, backup, or retain this data on external databases.
* You can permanently delete all of this data at any time by uninstalling the application or clearing the application data/cache in your device settings.

---

## 7. Changes to This Privacy Policy

We may update this Privacy Policy from time to time. Any updates will be posted to our official documentation. Your continued use of the application after an update constitutes acceptance of the modified Privacy Policy.

---

## 8. Contact Information

If you have any questions or feedback regarding this Privacy Policy, please contact us:
* **Developer/Publisher:** LunaWorks (Colby Cabrera)
* **Support Email:** colbycabrera.wd@gmail.com
* **Project Page:** https://colbycabrera.github.io/sight-reading-trainer-app
