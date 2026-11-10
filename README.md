# Publish CasMY on GitHub Pages

1. Extract CasMY-GitHub.zip on your computer.
2. Create a GitHub repository named casmy (choose Public if using free GitHub Pages).
3. Select Add file > Upload files. Upload the extracted files directly into the repository root, not the ZIP or an extra containing folder. Ensure index.html, app.js and stations.json are at the same level. Include .nojekyll if your file picker shows it.
4. Commit the uploaded files to main.
5. Open Settings > Pages. Under Build and deployment choose Deploy from a branch, select main and / (root), then Save.
6. Wait for the Pages deployment to complete; use the website link shown in Settings > Pages.
7. Open the HTTPS website and test a station search, filters, favourites and navigation. Allow browser location permission when using Use my location.

Do not double-click index.html to test the directory: loading stations.json requires an HTTP server. For local testing, run python3 -m http.server 8000 in the extracted folder, then open http://localhost:8000.

No npm install, build step or API key is needed. Internet access is needed for map tiles, Leaflet and fonts. Favourites are browser-specific. GitHub Pages publication makes the website publicly accessible; it does not inherit the private access of the original CasMY preview.

Troubleshooting: For a 404, check that the filename is exactly index.html and the Pages source is main / (root). For Directory unavailable, confirm stations.json was uploaded beside index.html. For denied location, enable permission for the HTTPS site. For updates, upload replacement files with the same names and wait for redeployment.

GitHub documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

# CasMY
Responsive static Malaysia EV charging finder. Serve the dist directory over HTTPS. For GitHub Pages copy dist contents to the repository root.

Includes 1,374 published location records, state and operator filters, AC/DC filters, browser favourites, geolocation-based straight-line sorting, and Google Maps/Waze directions. The published source records date from March 2023 to May 2025 and were retrieved on 10 November 2026. This is a historical directory MVP, not current operational verification.

Source: https://services3.arcgis.com/g3kI4O97ITe9dDVx/ArcGIS/rest/services/Distribution_EV_Charging_Stations_in_Malaysia_WFL1/FeatureServer/0
Source object IDs and individual record dates are preserved. Only Existing records with valid Malaysian-range coordinates are included. Source state labels are retained. Dataset contains restricted/residential locations; confirm public access with the operator. Source metadata and reuse terms should be reviewed before wider commercial redistribution.

No live availability, connector specifications, power ratings, prices, reservations or payments are provided. AC/DC is a charging category, not connector compatibility. An operator data integration is needed for these capabilities.

Dependencies: Leaflet via unpkg, OpenStreetMap tiles and attribution, Google Fonts. Favourites remain in the current browser. Location is requested on button click and is not persisted; viewed map areas affect tile requests. Directions send selected station coordinates to the chosen navigation service.

## Visual theme and logo
Bright blue (#005BEA), white and deep navy (#101629), with a cyan accent (#48E0D0), inspired by the supplied reference. The custom CasMY identity pairs a C-shaped charging symbol and energy bolt with a clean wordmark. logo.svg is the full horizontal logo; favicon.svg is the compact icon. Both are scalable SVG assets.

To update an existing GitHub deployment, replace index.html and app.js, and upload logo.svg and favicon.svg beside them. All relative asset paths support GitHub project Pages. The existing station dataset is unchanged.
