# SpendNod favicons

Drop these files at your site root (or wherever your static assets live), then add this to your `<head>`:

```html
<link rel="icon" type="image/svg+xml" href="/favicon.svg">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32.png">
<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16.png">
<link rel="shortcut icon" href="/favicon.ico">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
<link rel="manifest" href="/site.webmanifest">
<meta name="theme-color" content="#0B0F1A">
```

## Files

| File | Purpose |
|---|---|
| `favicon.svg` | Modern primary — scales infinitely, used by Chrome/Firefox/Safari |
| `favicon.ico` | Legacy fallback (16/32/48 multi-size) |
| `favicon-16.png`, `favicon-32.png`, `favicon-48.png`, `favicon-64.png` | Explicit PNG sizes |
| `apple-touch-icon.png` (180×180) | iOS home screen — has navy rounded background |
| `apple-touch-icon.svg` | Vector version of the iOS icon |
| `android-chrome-192.png`, `android-chrome-512.png` | Android home screen / PWA |
| `transparent-180.png`, `transparent-192.png`, `transparent-512.png` | No-background versions for use on custom surfaces |
| `site.webmanifest` | PWA manifest pointing at the Android icons |

The mark uses the brand gradient (blue → cyan → teal) on a transparent background by default; iOS/Android variants get a navy `#0B0F1A` rounded bezel because those platforms expect a filled icon.
