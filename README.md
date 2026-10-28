# House Visit Summary

A single-page tool for real estate agents to log properties viewed with a
buyer during an outing and export a clean, branded PDF report at the end.

- Add properties with address, price, size, bedrooms/bathrooms
- Flag nearby MRT, Food Court, Bus Stop, and other amenities with
  distance and walking time (fill in manually, or auto-estimate when
  this page is opened inside the Claude app)
- Generate a PDF with per-property cards and a comparison table of
  nearby amenities, one column per location type
- Nothing is stored — the session lives only in the browser tab, and
  the PDF is the record

## Deploying

This is a static site: a single `index.html` with no build step.

1. Push this repo to GitHub (already done if you're reading this on GitHub).
2. Import the repo in [Vercel](https://vercel.com/new) — no framework
   preset needed, Vercel serves `index.html` as-is.
3. `vercel.json` sets clean URLs and a couple of safe default headers;
   no further configuration is required.

## Notes on the PDF

The PDF is generated client-side with [jsPDF](https://github.com/parallax/jsPDF),
loaded from cdnjs. Distances and walking times you haven't measured
yourself are estimates — the report says so, and they should be
verified before sharing with a buyer.
