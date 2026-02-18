# 🇩🇪 German Mobile Provider List (MNP/Porting Codes)

A highly structured, clean, and community-maintained JSON list of German mobile phone providers.

**Primary Goal:** To help people find the correct **"Anbieterkennung"** (Provider Code) required to port a mobile number from one carrier to another (Rufnummernmitnahme).

🔗 **[Live View / Search Tool](https://providers.ikels.org)**

---

## 🧐 Why does this exist?

The German mobile market is complex. There are only 4 physical network operators (Telekom, Vodafone, O2, 1&1), but hundreds of "Resellers" (Aldi Talk, Congstar, sim.de, etc.).

When you want to **keep your phone number** (Mobile Number Portability / MNP) while switching contracts, the new provider asks for your **"Bisheriger Anbieter"** (Old Provider).

*   Sometimes you need to select the *brand name*.
*   Sometimes you need the *parent company* (e.g., Drillisch).
*   Sometimes you need a specific *technical code*.

This list maps the **Brand Name** to the correct **Technical Code** and the **Physical Network**.

## 🌍 For Expats & Foreigners

If you are living in Germany and struggling with the forms, here is a translation of the key terms used in this data:

| German Term | English Equivalent | Context |
| :--- | :--- | :--- |
| **Anbieter** | Provider / Carrier | The company sending you the bill. |
| **Anbieterkennung** | Porting Code / Short Code | The internal ID used to route your number (e.g., `VICT`, `1UN1`). |
| **Rufnummernmitnahme** | Number Porting (MNP) | The process of keeping your number when switching. |
| **Netz** | Network | The physical infrastructure (Signal) you are using. |
| **D1** | Telekom Network | Generally considered the best coverage. |
| **D2** | Vodafone Network | |
| **O2 / Telefónica** | O2 Network | Very common for budget providers (Drillisch/Aldi). |
| **1&1 5G** | 1&1 Network | The newest network (roams on Vodafone/O2 where 5G is missing). |

### ⚠️ Common Pitfalls (Read this!)

*   **Drillisch Brands:** If you have a contract with *sim.de, handyvertrag.de, winSIM, yourfone*, etc., your actual provider for porting is often listed as **Drillisch Online GmbH** or uses the code **`VICT`**.
*   **WEB.DE / GMX:** These are tricky!
    *   If you have a standard 24-month contract, you are likely with **1&1** (`1UN1`).
    *   If you have a "FreePhone" or monthly cancelable Flex-Tariff, you are likely with **Drillisch** (`VICT`). *Check your invoice!*

---

## 💻 Data Structure (`providers.json`)

The data is stored in a simple JSON array.

```json
[
  {
    "name": "sim.de",       // The commercial brand name
    "code": "VICT",         // The code needed for porting (Anbieterkennung)
    "net":  "O2"            // The physical network (D1, D2, O2, 1&1)
  }
]
```

## 🚀 How to Contribute

Is a provider missing? Did a provider switch networks (e.g., from O2 to Vodafone)?

1.  **Edit the Data:** Open `providers.json` in this repo.
2.  **Add/Fix the Entry:** Keep the structure clean.
3.  **Submit a PR:** Create a Pull Request.
4.  **Auto-Update:** An automated workflow will verify the JSON and update the "Last Updated" date on the website.

---

## ⚖️ Disclaimer

This data is gathered from community research, support forums, and provider documents.

*   **No Warranty:** We do not guarantee that the porting codes are 100% correct for every individual contract type.
*   **Verify:** Always check your termination confirmation (Kündigungsbestätigung) or invoice for the exact provider name.
