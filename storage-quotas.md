# Client's side Storage Quotas

There is one quota for all storages.

### Quota includes:
- All the data from APIs:
    - Local Storage.
    - IndexedDB.
    - Cache Storage.
    - FileSystem (Origin Private FileSystem).
- Service Worker registrations.
- Web App Manifests from installed PWAs (like icon).

### Quota does not include:
- Cookies.
- Files cached by the browser.
- Session storage.
- Files created with the FileSystem Access API (on the real FS not Safari's Origin Private FS).


### Quotas per browser

- Chromium: 60% of total disk space per origin. Domain and its subdomains all have their own quotas.
- Firefox: 50% of total disk space with maximum of 2GB per group (eTLD+1). So domain and its subdomains all have the same quota.
- Safari: 1GB per partition (origin) with increments of 200mb with user's permission.