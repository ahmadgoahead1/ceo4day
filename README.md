# ceo4day
This is the game for the LOB of MBA program

# CEO for a Day: LIVE (phone answering, Kahoot style)

Two files:
- `host.html` is the projector screen: the game, music, scores and QR code.
- `index.html` is the phone buzzer page the 4 spokespeople open.

Phones talk to the laptop through the free PeerJS relay service (`0.peerjs.com`), so **the laptop and the phones need internet**. They don't need to be on the same Wi-Fi. Nobody needs an account or an app.

## One-time setup: put the folder online (GitHub Pages, free, ~5 min)
1. Sign in at github.com and create a new **public** repository, e.g. `ceo4day`.
2. Click **Add file → Upload files** and drag in `host.html` and `index.html`. Click **Commit**.
3. Go to **Settings → Pages**. Under "Branch", choose `main` and `/ (root)`, then click **Save**.
4. After about a minute the site is live at `https://<your-username>.github.io/ceo4day/`.
   - Projector: open `https://<your-username>.github.io/ceo4day/host.html`
   - Phones: they just scan the QR code, which points at `index.html` with the join code.

Opened from GitHub Pages, `host.html` builds the QR link by itself. If you open `host.html` from your laptop's disk instead, paste the site link (`https://<your-username>.github.io/ceo4day/`) into the **Phone page link** box on the Teams screen once. The browser remembers it.

Note: the repository is public, so anyone with the link can see the quiz questions. Upload it after you've finished editing, or delete the repository after class.

## In class
1. Open `host.html` and press **Full screen**. The top-right chip turns green: "Join code ABCD · 0 phones".
2. On the **Teams** screen, each team's spokesperson scans the QR code and taps their team colour. Every team brick on screen shows 📱 1 when it's connected.
3. Phone buttons unlock only when you start the timer. **The first tap is final.**
   - The laptop stamps each answer when it arrives, so the +50 (or lightning +100) speed bonus is automatic.
   - Teams' choices stay hidden on the projector until you reveal.
   - When all 4 teams have answered, the timer stops by itself.
4. After each reveal, phones show Correct or Not this time, the points won, and the team's rank. At the end they show the final place.

## If something goes wrong
- **A phone drops:** reload the page. It rejoins the same room and team automatically.
- **A team has no phone or bad signal:** that team holds up fingers as before, and you enter its answer with R/B/Y/G then 1/2/3 (or click the team's button). Hand-entered and phone answers mix freely.
- **No internet at all:** the chip says "Phones offline · play by hand". The game still runs fully by hand, or use the offline backup `../GP5_Icebreaker_CEO-for-a-Day.html`.
- Each time `host.html` is reloaded it gets a **new join code**, so phones must scan again. Don't reload the projector mid-game.

## Tested
A headless Chrome run with one host and 4 phones went through the real PeerJS service. Everything checked passed:
- join, team pick and phone counts;
- answers hidden until the reveal;
- automatic timer stop when all teams answered;
- speed bonus;
- first tap is final;
- results and podium showing on the phones.

Not yet tested: real phones on the campus network. Do one run-through with 2 phones before class.
