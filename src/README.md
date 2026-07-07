# Marketing graphics pipeline

Compositions in `mkt/` (hero.html, premium.html, stats.html + base.css) render
the email/marketing graphics from live-app screen captures in `screens/`.

Render at retina 2x with headless Chrome:

    CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
    "$CHROME" --headless=new --disable-gpu --force-device-scale-factor=2 \
      --window-size=1200,900 --screenshot=premium-2x.png "file://$PWD/mkt/premium.html"

(window-size: hero 1200x660, premium 1200x900, stats 1200x190.)
Convert: `sips -s format jpeg -s formatOptions 86 premium-2x.png --out ../email/premium.jpg`

Screen captures came from the iOS Simulator (Release build, live data,
premium unlocked via RevenueCat promotional entitlement). Fresh captures:
see docs/launch/WELCOME-EMAIL-SETUP.md in the StockPulsePro repo.
