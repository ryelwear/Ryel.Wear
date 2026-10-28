RYEL WEAR WEBSITE — CUSTOMER EMAIL LOGIN VERSION

WHAT THIS VERSION DOES
- Adds Customer Login using Supabase email OTP verification.
- Requires the customer to verify their email and sign in before opening/placing an order.
- Uses the signed-in email in the order form.
- Keeps the existing order submission flow to Google Sheets via Google Apps Script. Orders are NOT saved in Supabase.
- Keeps the existing product images and storefront design.

UPLOAD TO GITHUB PAGES
1. Download and unzip this package.
2. Upload index.html and the entire images folder into the ROOT of your GitHub Pages repository (not inside another nested folder).
3. Commit/save the changes and wait for GitHub Pages to publish.

SUPABASE EMAIL OTP SETUP (IMPORTANT)
Your Supabase project is already configured in the website code. The browser uses the public publishable key; do not put a service-role/secret key in the website.
1. Open Supabase Dashboard and select project rlxmcpmucjawqjhotwrn.
2. Go to Authentication > Email Templates > Magic Link (wording may vary by dashboard version).
3. To send a numeric email code instead of only a link, set the email template body to include {{ .Token }} (for example: "Your Ryel Wear verification code is {{ .Token }}"). Do not use only {{ .ConfirmationURL }} for this OTP screen.
4. Save the template. Keep the Email provider enabled under Authentication > Sign In / Providers.
5. In Authentication > URL Configuration, keep Site URL and Redirect URL set to https://ryelwear.github.io/Ryel.Wear/.
6. Test with your own email. Check Spam/Junk if the code does not arrive.

GOOGLE SHEETS ORDER FLOW
The existing Apps Script URL in index.html is:
https://script.google.com/macros/s/AKfycbzT-5zj8qQ3plNtsfMNiZM_HDEhkIFJrjhVsgKz0TVSvFKv06I3kZOakWv-3ok_e14m/exec
If your Google Sheets order flow is already working, leave the Apps Script deployment alone. If you need to update it, open the linked spreadsheet > Extensions > Apps Script, replace Code.gs with Apps_Script_Code.gs, save, then Deploy > Manage deployments > Edit > New version > Deploy. Configure as Web app, Execute as: Me, access: Anyone, and authorize permissions if asked.

IMPORTANT NOTES
- Supabase is only used for authentication/session. Order data remains in Google Sheets.
- The website uses the Supabase publishable key, which is intended for browser use. Never add a Supabase service-role key to index.html.
- Google Apps Script uses a no-cors request, so the browser cannot confirm the server response. After a test order, verify the row in Google Sheets.
- Test using your own email and a test order before launch.
