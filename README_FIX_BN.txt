RYEL WEAR WEBSITE — FIXED PACKAGE

1. GitHub Pages: upload index.html AND the entire images/ folder into the repository root. Do not upload only index.html. Keep filenames exactly as supplied (lowercase).
2. Google Sheet fields: this package includes Apps_Script_Code.gs, which writes Timestamp, Customer Name, Phone, Address, Area, Product, Size, Quantity, Payment Method, Transaction ID, Product Total, Delivery Charge, Grand Total.
3. To fix sheet columns, open the Apps Script project attached to your Ryel Wear Orders sheet, replace the old code with Apps_Script_Code.gs, Save, then Deploy > Manage deployments > Edit (pencil) > Version: New version > Deploy. Keep access set to Anyone if that is how your current web app is configured.
4. Test with quantity 4 and an online payment. Expected product total = ৳5,396. Grand total = ৳5,476 inside Dhaka, ৳5,516 Sub-Dhaka, or ৳5,546 outside Dhaka.
5. Online payments are recorded as the selected method and manually verified. The website cannot automatically confirm that money arrived.
