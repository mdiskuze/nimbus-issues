# Nimbus

**Hyper-local weather for Lunde, Kramfors and Härnösand.**

Radar first, honest about how much it knows, and built to answer one question before you open
anything: do you need a coat.

---

## Download

See [Releases](https://github.com/mdiskuze/nimbus-issues/releases) for the latest APK.

> Requires Android 10+ (API 29).

Android will warn you on install, because the app is not from the Play Store and Play Protect has
never seen its signing key. In that dialog the small **Install anyway** text is the action, and the
prominent **Got it** button cancels. If it refuses outright, turn off **Play Store → your profile →
Play Protect → Scan apps with Play Protect** for the install.

After the first install, **Nastaveni → Aktualizace → Zkontrolovat verzi** finds later versions here.

---

## Setup

None. No account, no API keys, no server, no telemetry. Every source it uses is free and needs no
registration, and everything stays on the device.

---

## Why it exists

Every general forecast app renders a model cell kilometres wide over terrain where the coast, the
Ångermanälven valley and the hills make the weather local. Lunde and Kramfors are 8 km apart and
sit 65 m and 23 m above the sea. Most models cannot tell them apart at all.

Nimbus is not a better general weather app. It is an accurate app for one small area, and it takes
every trade that follows from that.

---

## What it does

**Ted** — one sentence saying whether you will get wet and for how long you can count on it.
Temperature with the feels-like, wind with gusts and direction, and the 3 h pressure tendency, which
is the number a wall barometer's spare hand measures. Below that a 24 hour chart of precipitation
over a confidence band, then a strip of days that open into night, morning, afternoon and evening.

**Radar** — the Swedish radar composite cropped around your place, over a coastline and lake map,
with distance rings and a marker for each place. A play button animates the last two hours, and the
slider runs 24 hours back in 5 minute steps.

**Zdroje** — what every number on screen is, which service it comes from, and what it is worth.

**Nastaveni** — default place, radar span, and update checking.

Plus a home-screen widget and a notification when radar puts rain inside 90 minutes.

---

## How it decides what to trust

Every value carries a confidence number, and the app never states more than the data supports.

- **0 to 2 hours** comes from radar extrapolation, not a model, which is the only thing that can
  answer "if I leave now".
- **Beyond that** comes from a 1 km model, the only free one whose grid separates the three places.
- **Confidence** for model hours is how unanimous a 51 member ensemble is, discounted by how far
  ahead it is looking, because all members share the same physics and unanimity ages. For the radar
  layer it depends on how settled the weather is, not only on the clock: persistence of "nothing is
  happening" is a genuinely easy forecast, scattered showers are not.
- **A source that fails renders as unavailable.** Never as zero, never as a guess. An empty radar
  picture still says "clear to 150 km" rather than showing nothing.

There is no weather station in Lunde or Kramfors. The nearest rain gauge is 27.8 km away and the
nearest barometer 35.1 km away at a different elevation, so the app is honest that it cannot check
itself against a local measurement.

---

## Issues

Bug reports and ideas go in [Issues](https://github.com/mdiskuze/nimbus-issues/issues).

---

## Data credits

Weather data from MET Norway (NLOD / CC BY 4.0), Open-Meteo (CC BY 4.0) and SMHI (CC BY 4.0).
Coastline and lake geometry from OpenStreetMap contributors (ODbL).
