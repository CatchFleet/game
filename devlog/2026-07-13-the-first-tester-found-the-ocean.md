# Devlog 2: The first tester found the ocean

*July 13, 2026*

Our first Alfa tester came on the air this weekend. Their station turned out
to be in Barcelona, which we were quietly hoping for: dense European traffic
we had never sampled. Within two hours they had 246 aircraft in the log, a
unicorn on the wall, and a question we could not ignore: why does my station
say I caught something 4,900 kilometers away?

A radio horizon tops out around 450 kilometers. 4,900 is not a lucky bounce;
it is physics saying no. The trail led to a dump1090 running without a
receiver location. Without that reference, weak frames decode into positions
scattered over the Gulf of Guinea, and our pipeline trusted them. Fifteen of
those ghosts were not even aircraft; none of their hex codes exist in a
680,000-row registry. One of them had quietly claimed all four tiers of the
DX range patch in twelve minutes. The tester earned tier one for real a few
hours later, at 159 kilometers, and that one stays.

What shipped in response, over three deploys:

- **Distance verification.** A claim beyond the reception horizon is stored
  but waits for review instead of posing as a record. You see the pending
  state on your own catches; nothing counts toward Range patches until it is
  verified.
- **Noise gates.** A single frame from a hex no registry has ever heard of is
  filtered before it touches your collection. Real single-frame catches from
  known airframes still land.
- **Listener 0.5.0.** Catches survive network hiccups with automatic retries.
  The Listener warns at startup when your dump1090 has no location set. A
  lockout no longer wipes your station link (that one caused a
  reopen-the-browser loop our tester got to enjoy). The terminal now reads
  like a catch log, and your dashboard shows an Update available tag when a
  newer Listener exists.
- **Boarding by email.** Standby invitations now carry your boarding code and
  a link that fills the signup form. New crew get apply access automatically;
  no more manual allowlist edits behind the curtain.

Honesty section, as promised. Two releases of the Listener shipped binaries
that reported an older internal version than their tag, which is why 0.5.0
exists: tag, code and binary agree again. And a permissions gap that passed
every local test would have silently broken the new review queue in
production; it was caught in review only because we now assume local green
means nothing until the production role has been checked. Both lessons are
now checklist items.

Next: the same tester's data gets re-analyzed on July 19 to calibrate the
deferred patch thresholds against a real week of reception, and the Flight
Manual gets a full overhaul. The game grew more this weekend than in the
quiet week before it. Testers do that.
