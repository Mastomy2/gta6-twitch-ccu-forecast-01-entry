# gta6-twitch-ccu-forecast-01-entry

[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/Mastomy2/gta6-twitch-ccu-forecast-01-entry/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/Mastomy2/gta6-twitch-ccu-forecast-01-entry/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

Forecast of GTA VI's launch-day Twitch viewers, hour by hour, for make.fun's "Forecast GTA VI's launch-day Twitch viewers" bounty. A Python 3.13 stdlib-only program: for each of hours 2–24 it writes five quantiles (5%, 25%, 50%, 75%, 95%) of that hour's concurrent viewers in the Grand Theft Auto VI category, given hour 1's print and the case's comparables.

Method: similarity-weighted empirical quantiles of past big launches' release-day shapes. Each comparable launch contributes its log-ratio curve ln(viewers_h / viewers_1), weighted by how close its own hour-1 print is to this case's (Gaussian kernel, sigma 1.0 on log hour-1). Big hour-1 launches stay near flat all day; small hour-1 launches (rolling midnight unlock) explode by evening — the weighting follows the shape of launches of the same size. Leave-one-out over the kit's 38 comparables: mean pinball loss 0.405 vs the house baseline's 0.930; on big launches alone 0.216 vs 0.261. Referral code: 94ztz8n6.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=94ztz8n6&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
