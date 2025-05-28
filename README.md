# 📦 App Store Review Scraper 
This project is a **Python-based scraper** that collects user reviews for any iOS application from multiple country-specific versions of the **Apple App Store** using the [`app-store-web-scraper`].

---

## 🔧 Configuration

Before running the script, update the following variables at the top of the file:

```python
# App configuration – put your target App Store ID and app name below
app_id = PUT_APP_ID_HERE           # e.g., 1497518128
app_name = "PUT_APP_NAME_HERE"     # e.g., "Emirates NBD Bank app store"
````

You can find the `app_id` in the App Store URL of the target application:

```
https://apps.apple.com/ae/app/emirates-nbd/id1497518128
                                           └──────────────┘
                                              app_id
```

---

## 🚀 What the script does

1. Connects to the App Store using the provided `app_id`.
2. Iterates through a list of predefined country codes (e.g., `ae`, `us`, `gb`, `in`, etc.).
3. For each country:

   * Tries to fetch available public reviews for the app.
   * Handles errors gracefully if reviews are not available.
4. Collects all reviews into a single unified table.
5. Saves the collected reviews into a clean CSV file named based on the app name.

---

## 📊 Review details collected

Each row in the output file contains:

| Field   | Description                 |
| ------- | --------------------------- |
| Name    | Username of the reviewer    |
| Comment | The actual review text      |
| Rating  | Star rating given (1 to 5)  |
| Date    | Date the review was posted  |
| Country | App Store country of origin |

---

## 📈 Additional Feature

The script also includes a **review counter** function that:

* Counts the number of reviews fetched from each country.
* Calculates the total number of reviews collected.
* Helps assess where the app has the most user engagement.

---

## 🧰 Technologies Used

* **Python 3.10+**
* [`pandas`]
* [`app-store-web-scraper`](https://pypi.org/project/app-store-web-scraper/) – App Store review scraping

---

## 📁 Output

After running the script, the following file is generated:

```
<app_name_in_snake_case>_reviews.csv
```

Example:

```
emirates_nbd_bank_app_store_reviews.csv
```

---

## ❗ Limitations

* The script only collects reviews that are publicly visible via the App Store's web interface.
* Apple may limit the total number of reviews that are retrievable (typically up to 1000).
* Some countries may not return any reviews or could cause parsing errors — these are handled automatically.

---

## ✅ How to Run

1. Install required packages:

```bash
pip install app-store-web-scraper pandas
```

2. Edit the script to add your `app_id` and `app_name`.

3. Run the script:

```bash
python your_script.py
```

---
