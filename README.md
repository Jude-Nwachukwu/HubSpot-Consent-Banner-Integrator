# Unofficial HubSpot Consent Banner Integrator (GTM Custom Tag Template)

The **HubSpot Consent Banner Integrator** is a Google Tag Manager (GTM) custom tag template that lets you control and synchronize HubSpot's cookie consent banner with your website’s consent management system or Google Consent Mode signals.  

This template simplifies how you handle consent categories (Analytics, Advertisement, and Functionality) within HubSpot and ensures consistent behavior across multiple tracking and analytics tools.

Developed with ❤️ by **Jude Nwachukwu Onyejekwe** and the **DumbData Team** for **[DumbData](https://dumbdata.co/)**. 


---

## 🚀 Features

- **Integrate Third-Party Consent Banners**  
  Seamlessly link your external consent banner or CMP with HubSpot using either manual signals or Google Consent Mode.

- **Use Google Consent Mode Signals**  
  Automatically sync HubSpot consent categories (`analytics`, `advertisement`, `functionality`) with their respective Google Consent Mode states.

- **Manual Consent Signal Configuration**  
  Define each HubSpot consent category manually using dropdown selectors to specify “Granted”, “Denied”, “True”, or “False”.

- **Show HubSpot Banner on Demand**  
  Trigger HubSpot’s cookie consent banner programmatically to re-display it when users need to update their preferences.

- **Revoke Cookie Consent**  
  Programmatically revoke all HubSpot tracking consent, resetting the visitor’s consent state.

- **Optional Console Logging**  
  Enable or disable console output for debugging directly from the tag configuration.

---

## 📥 Download and Import

1. **Download Template File**  
   - From this repository, download the `template.tpl` file.

2. **Import into GTM**  
   - In your GTM workspace, go to **Templates → Tag Templates → New**.  
   - Click the **More Actions (⋮)** menu → **Import**.  
   - Select the downloaded `template.tpl` file.

3. **Save and Publish**  
   - Review the permissions and save the imported template.  
   - You can now add it as a tag to your GTM container.

---

## ⚙️ Configuration Guide

### 1. **Select HubSpot Cookie Banner API Action**
Choose the primary action you want to perform using the **Select HubSpot Cookie Banner API Action** dropdown:
- **Integrate Your Own Consent Banner With HubSpot**  
  Connect your third-party consent banner or system with HubSpot.
- **Show HubSpot Consent Banner**  
  Programmatically trigger the HubSpot banner to appear.
- **Revoke Cookie Consent**  
  Reset all HubSpot cookie consent states.

---

### 2. **Select HubSpot Cookie Banner Integration Method**
If you choose **Integrate Your Own Consent Banner With HubSpot**, you must select how the integration works:
- **Use Google Consent Mode Signals**  
  Automatically maps HubSpot consent states using Google’s `isConsentGranted` API.
- **Manually Configure Consent Signals**  
  Lets you define each consent category manually.

---

### 3. **Configure Your HubSpot Consent Signals Using Your Consent Banner**
If using **Manual Configuration**, specify each category:
- **Advertisement** – Determines whether advertising cookies are permitted.  
  Options: *Granted*, *Denied*, *True*, *False*  
- **Analytics** – Controls analytics cookie usage.  
  Options: *Granted*, *Denied*, *True*, *False*  
- **Functionality** – Governs site functionality cookies.  
  Options: *Granted*, *Denied*, *True*, *False*

When “Granted” or “True” is selected, the tag sends a `true` signal to HubSpot.  
When “Denied” or “False” is selected, it sends `false`.

---

### 4. **Optional Configuration**
Use the **Optional Configuration** section to manage tag debugging:
- **Disable Console Logging** – Check this option to suppress console messages when the tag executes.

---

## 🧠 Example Use Cases

### 🟢 Use Case 1: Integrate a Third-Party CMP
If your website uses another Consent Management Platform (CMP) such as OneTrust or Cookiebot, you can use this tag to forward those consent states to HubSpot automatically.  
Choose:
- **Action:** *Integrate Your Own Consent Banner With HubSpot*  
- **Integration Method:** *Manually Configure Consent Signals*  
Then map each category (Advertisement, Analytics, Functionality) based on your CMP’s consent state.

---

### 🟣 Use Case 2: Sync With Google Consent Mode
When your site uses Google Consent Mode (v2), this tag automatically fetches consent states (`ad_storage`, `analytics_storage`, `functionality_storage`) from Google’s API and updates HubSpot accordingly.  
Choose:
- **Action:** *Integrate Your Own Consent Banner With HubSpot*  
- **Integration Method:** *Use Google Consent Mode Signals*

---

### 🔵 Use Case 3: Allow Users to Reopen the HubSpot Banner
If you want to give users an option to review or change their consent preferences:
- **Action:** *Show HubSpot Consent Banner*  
You can trigger this tag via a button click or link (e.g., “Change Cookie Settings”).

---

### 🔴 Use Case 4: Revoke All HubSpot Consent
If users withdraw consent completely, trigger this tag with:
- **Action:** *Revoke Cookie Consent*  
This will clear HubSpot tracking cookies and reset consent preferences.

---

## 🪪 License
This GTM template is distributed under the **Apache 2.0 License**.  
See the [LICENSE](./LICENSE) file for details.

---

## 👤 Author
Developed with ❤️ by **Jude Nwachukwu Onyejekwe** and the **DumbData Team** for **[DumbData](https://dumbdata.co/)**. 
Designed for privacy-friendly, compliant integration between **HubSpot** and **Google Tag Manager**.
