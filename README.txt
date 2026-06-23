DEALNEST-STYLE MARKETPLACE SITE — Razorpay-ready
=================================================

This is a self-contained static website (7 HTML pages, no build step, no
dependencies). Each page has its CSS inlined, so you can drop the whole folder
straight onto Vercel (or Netlify, Cloudflare Pages, GitHub Pages, etc.).

PAGES
-----
  index.html      Home (describes the marketplace — this is what the reviewer sees first)
  pricing.html    Pricing / products page
  contact.html    Contact Us + Grievance Officer
  terms.html      Terms & Conditions
  privacy.html    Privacy Policy
  refunds.html    Refund & Cancellation Policy
  shipping.html   Service Delivery (shipping) Policy


STEP 1 — REPLACE THESE 8 PLACEHOLDERS (find & replace across all files)
----------------------------------------------------------------------
Do a find-and-replace in your editor (VS Code: Ctrl/Cmd+Shift+H, "replace in
files") for each token below. THE FIRST FOUR MUST EXACTLY MATCH YOUR RAZORPAY
KYC — the reviewer cross-checks them. Mismatches = rejection.

  {{COMPANY}}         -> Legal registered entity name, exactly as on the PAN
                         used for KYC. e.g. "DealNest Technologies Private Limited"
  {{ADDRESS}}         -> Full registered business address (must match KYC)
  {{EMAIL}}           -> A real, monitored support email (e.g. support@yourdomain.in)
  {{PHONE}}           -> A real contact phone number (e.g. +91 98765 43210)
  {{APP_NAME}}        -> Your app / brand name (e.g. "DealNest")
  {{GRIEVANCE_NAME}}  -> Name of your Grievance Officer (a real person)
  {{LAST_UPDATED}}    -> Today's date (e.g. "22 June 2026")
  {{YEAR}}            -> Current year for the footer copyright (e.g. "2026")


STEP 2 — REVIEW THE REFUND PAGE
-------------------------------
Open refunds.html and make the timelines match what you ACTUALLY do. The
default says refunds are processed in 5–7 business days and requests are
accepted within 7 days. Razorpay specifically checks this page for clear,
real timelines. Adjust the numbers if yours differ, then delete the yellow
"Note for the business owner" box. Do the same on pricing.html (set your real
plans/prices and remove its yellow note).


STEP 3 — DEPLOY TO VERCEL
-------------------------
Option A (no Git, fastest):
  1. Install the CLI:  npm i -g vercel
  2. In this folder:   vercel
  3. Follow the prompts. Then:  vercel --prod
  4. You'll get a live URL like https://your-project.vercel.app

Option B (drag & drop):
  1. Go to vercel.com -> Add New -> Project
  2. Drag this folder in (it's a static site — no framework needed)
  3. Deploy -> copy the live URL


STEP 4 — SUBMIT TO RAZORPAY
---------------------------
In the Razorpay Dashboard: Account & Settings -> Business website details ->
add your live URL. When it asks for individual policy links, use:

  Website / app : https://your-project.vercel.app
  Terms         : https://your-project.vercel.app/terms.html
  Privacy       : https://your-project.vercel.app/privacy.html
  Refund/Cancel : https://your-project.vercel.app/refunds.html
  Shipping      : https://your-project.vercel.app/shipping.html
  Contact       : https://your-project.vercel.app/contact.html

Submit for review. Verification can take up to ~3 working days, after which
"Generate Key" unlocks in Live Mode.

That's it.
