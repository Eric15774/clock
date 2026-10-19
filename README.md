# Classroom Clock

A full-screen time, date, and weather display for a classroom screen.

Live at: **https://clock.longwell.io**

## What it shows

- Large clock with seconds and AM/PM
- Today's date
- Current temperature, conditions, feels-like, wind, and humidity
- 4-day forecast with highs, lows, and chance of rain

## How it works

- Single file: `index.html`. No build step, no libraries.
- Weather comes from [Open-Meteo](https://open-meteo.com), which is free and needs no API key.
- Weather refreshes every 10 minutes. If the network drops, the last reading stays on screen and it retries every minute.
- The page reloads itself at 3 AM each day so it stays fresh on a screen left running.
- The mouse cursor is hidden over the page.

## Changing the location

Edit the `CONFIG` block near the top of the script in `index.html`:

```js
const CONFIG = {
  latitude: 40.765,
  longitude: -79.535,
  placeName: "Ford City, PA",
  timezone: "America/New_York",
  showSeconds: true,
  weatherRefreshMinutes: 10
};
```

Or override it in the web address without editing the file:

```
https://clock.longwell.io/?lat=40.77&lon=-79.53&name=Ford%20City
```

## Using it on the classroom screen

1. Open https://clock.longwell.io in the browser.
2. Press **F11** for full screen.

## Hosting

Hosted on GitHub Pages with a custom domain.

- DNS: a **CNAME** record for `clock` pointing to `eric15774.github.io`
- Repo **Settings > Pages**: custom domain set to `clock.longwell.io`, with **Enforce HTTPS** checked
- Keep the `CNAME` file in the repo. Deleting it removes the custom domain.

## Credits

Weather data by [Open-Meteo.com](https://open-meteo.com) (CC BY 4.0).
