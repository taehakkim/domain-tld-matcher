---

# 🔍 Domain TLD Filter & Data Extractor

This Python script is designed to analyze a domain dataset (CSV format) and extract records based on specified Top-Level Domains (TLDs). Originally developed to notify customers via email regarding policy updates or other matters based on their domain TLDs, the current version is modified to extract and display unique expiration dates (`Expires`) as a placeholder for sensitive data.

---

## 📂 File Structure

* `asciodomainlist.csv`: Input CSV file containing domain information.
* `main.py`: Main Python script to process the CSV file and filter data based on TLDs.

---

## ✅ Features

* ✅ Reads a domain data sheet encoded in CP949 (e.g., for Korean-language files).
* ✅ Filters domains based on a custom list of European ccTLDs (e.g., `.at`, `.ch`, `.es`, etc.).
* ✅ Extracts unique `Expires` values for matched domains.
* ✅ Joins the results into a semicolon-separated string for convenient use (e.g., sending reminders or generating reports).

---

## 🛠 How to Use

1. Make sure you have **Python 3** installed.

2. Install pandas if you haven’t:

   ```bash
   pip install pandas
   ```

3. Place your input CSV file at the path:

   ```
   D:\도메인시트스플릿\asciodomainlist.csv
   ```

   Make sure it has a structure like:

   | Column1 | Column2 | Domain         | Expires    | ... |
   | ------- | ------- | -------------- | ---------- | --- |
   | ...     | ...     | example.com.es | 2025-09-10 | ... |

4. Run the script with jupyter notebook.
   
5. Output: A list of domains ending with your specified TLDs, and a unique list of their expiration dates.

---

## 🧠 Logic Overview

* The script trims the leading dot (`.`) from the TLD list.
* It checks if the domain (3rd column) ends with any of the given TLDs.
* Filters matching rows.
* Extracts unique expiration dates (`Expires` column).
* Joins them into a printable string.

---

## 📌 Example Output

```bash
2025-08-12; 2025-09-10; 2025-11-25
```

---

## 🔐 Notes

* All customer-sensitive information (such as email addresses) has been removed for privacy.
* Replace the `Expires` column with customer emails if using this script for notifications in production.

---

## 📄 License

This script is provided under the MIT License. Use freely, but at your own responsibility.

---

## 🤝 Contributing

Pull requests are welcome. If you find any bugs or want to improve the functionality (e.g., email extraction, multi-language support), feel free to fork and submit changes.

---

