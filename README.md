# jonathanhaggard.com

Static GitHub Pages redirect to <https://darlingjules.com/>.

The root page and the custom `404.html` send visitors from every old path to the new homepage. JavaScript preserves the query string and fragment, and uses `location.replace` so the old URL does not add an extra browser-history entry. The destination origin is fixed and cannot be supplied through query parameters.

If JavaScript is disabled, the HTML refresh and visible link lead to the new homepage without preserving the query string or fragment. GitHub Pages serves a missing path with an HTTP 404 before the browser redirect; this is a static-site redirect, not an HTTP 301/308.

## Publish

Publish the `main` branch, `/ (root)` folder in GitHub Pages. No build command or Actions workflow is needed. `CNAME` binds `jonathanhaggard.com`, and `.nojekyll` keeps the site as plain static files. Configure the domain's DNS for the Pages site, then enable HTTPS when GitHub's certificate is ready.

The intended HTTPS destination is always `https://darlingjules.com/`. Old paths are deliberately not copied to the destination because there is no confirmed path map for this domain.
