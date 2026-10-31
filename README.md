# jonathanhaggard.com

Static GitHub Pages redirect to <https://darlingjules.com/>.

The root page and the custom `404.html` send visitors from every old path to the new homepage. JavaScript preserves the query string and fragment, and uses `location.replace` so the old URL does not add an extra browser-history entry. The destination origin is fixed and cannot be supplied through query parameters.

If JavaScript is disabled, the HTML refresh and visible link lead to the new homepage without preserving the query string or fragment. GitHub Pages serves a missing path with an HTTP 404 before the browser redirect; this is a static-site redirect, not an HTTP 301/308.

## Publish

GitHub Pages publishes the `main` branch, `/ (root)` folder. No build command or custom Actions workflow is needed. `CNAME` binds `jonathanhaggard.com`, and `.nojekyll` keeps the site as plain static files. HTTPS is enforced; GitHub manages the certificate for the apex and `www` domains.

Namecheap BasicDNS holds the web records:

| Type | Host | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | julesdarling.github.io |

Keep the existing Google MX and DKIM records when changing web routing. GitHub redirects `www` to the apex before the page forwards to Darling Jules.

The intended HTTPS destination is always `https://darlingjules.com/`. Old paths are deliberately not copied to the destination because there is no confirmed path map for this domain.
