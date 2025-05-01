# ✅ Google Shopping Feed Project: SAGE Product Integration

## 📌 Project Summary

| Step    | Task                                              | Result                                                                 |
|---------|---------------------------------------------------|------------------------------------------------------------------------|
| Step 1  | Export product data from SAGE Website             | Success - obtained product IDs and SKUs, but no image URLs            |
| Step 2  | Tried building image URLs using Product ID        | Failed - image IDs do not match product IDs                           |
| Step 3  | Manually verified image URL structure             | Confirmed image asset IDs are separate from product IDs               |
| Step 4  | Tested with AWS Lambda                            | Blocked - SAGE rejected Lambda IPs                                    |
| Step 5  | Tested locally with .env API auth                 | Initially successful                                                  |
| Step 6  | Built script to fetch image IDs via API           | Partially successful - some IDs retrieved                             |
| Step 7  | Batch API calls triggered connection reset        | IP blocked by SAGE                                                    |
| Step 8  | Confirmed IP was blocked                          | Manual test showed repeated reset errors                              |
| Step 9  | Identified workarounds                            | Use VPN or mobile hotspot for IP rotation                             |

---

## 🛠 Tools & Technologies Used

- Excel (SAGE product export)
- Python 3.10
- `pandas`, `openpyxl`, `requests`, `python-dotenv`
- SAGE Connect API
- Custom Scripts:
  - `inject_image_urls.py`: adds image URLs using product IDs
  - `get_image_ids.py`: retrieves real image asset IDs via API
  - `test_sage_connection.py`: confirms API/IP connectivity

---

## ✅ What Worked

- Parsed Excel data successfully
- Injected valid image URLs after discovering asset IDs
- Successfully authenticated with SAGE Connect API locally (initially)
- Built logic for `image_link` and `additional_image_link` support

---

## ❌ What Didn’t Work

- Using `SAGEProductID` directly as `P` value in image URLs
- Hosting on AWS Lambda or VPS (IP blocking by SAGE)
- Repeated API requests from a single IP (triggered firewall block)

---

## 🚀 Next Steps

- Run script using VPN or mobile hotspot to avoid IP block
- Complete population of image URLs using correct asset IDs
- Generate and host XML feed for Google Merchant Center

---
