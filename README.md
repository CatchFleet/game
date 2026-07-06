# Catch Fleet

**Collect the invisible world.**

The sky above you is full of voices. Every airliner crossing your horizon
announces itself on 1090 MHz, to anyone who cares to listen. Catch Fleet is
a collection game about listening: you plug in a software-defined radio, run
a small Listener next to your decoder, and every aircraft your own antenna
catches fills your Dex.

It is deliberately **not a flight tracker**. Trackers show you everything,
instantly, and nothing feels earned. Here, only your own reception counts.
Every aircraft in your Dex physically flew through your sky, and your
station caught it.

🎟️ **Alpha is open, seats limited:** [playcatchfleet.com](https://playcatchfleet.com)
👀 **Browse a live Dex** from a real station: [playcatchfleet.com/sedergine/dex](https://playcatchfleet.com/sedergine/dex)
📖 **Flight Manual** (setup, honest requirements): [playcatchfleet.com/manual](https://playcatchfleet.com/manual)

## The repositories

| Repo | What it is |
| --- | --- |
| [game](https://github.com/catchfleet/game) | The game itself: Next.js app, catalog, resolver, Dex engine, design docs |
| [listener](https://github.com/catchfleet/listener) | The small bridge between your local ADS-B decoder (SBS1) and your Dex |

## Principles we build by

- **Real signal first.** No manual catches, no trading, no pay-to-win.
  Artificial progress never replaces real reception.
- **Honest uncertainty.** Every identification carries a confidence label,
  a source and a reason. Unknown aircraft become mystery signals, not
  errors, and can resolve later without losing your catch.
- **Privacy by design.** Raw frames never leave your machine; only bounded,
  summarized observations are posted. Station coordinates are never public.
- **Hardware is part of the game.** A ~$30 RTL-SDR with its stock antenna is
  a perfectly good starting station, and upgrading your setup shows up
  honestly in your collection.

## Built in the open, by one ham and a lot of AI

Catch Fleet is designed and run by [Meriç, TA3DIY](https://github.com/ta3diy),
an amateur radio operator, not a professional developer. The code is written
almost entirely by AI coding agents working from the design docs and reviews
you can read in these repositories. The game design, the catalog research
and every product decision are human. Judge the result for yourself.

---

*73, and happy catching.*
