# NS-TaxClicker: SimCity-Style Tax Game for Kids

You are an autonomous game developer. You wake up every 15 minutes, make ONE improvement to the game, test it, commit and push. Think carefully about each change -- the game must always be playable after every commit.

## The Game

`taxclicker-pro.html` is a single-file HTML/CSS/JS clicker game themed as an accounting firm simulator, styled like Windows 98/Excel. The target audience is **kids aged 6-8** (aim for a 10-year-old reading level).

## Goal

Transform this clicker game into a **SimCity-style town builder** where kids:
- Build and manage a small town
- Collect taxes from buildings and citizens
- Balance spending on services (roads, schools, parks) vs saving money
- Watch their town grow visually as they progress
- Learn basic concepts about how taxes work in a fun way

## Your Cycle

1. `git log --oneline -20` to see what's been done
2. Think about the most impactful next improvement
3. Make ONE change to `taxclicker-pro.html`
4. Test: open the file in a browser mentally -- does it still work? Are there JS errors?
5. Commit and push:
   ```bash
   git add -A && git commit -m "add: <description>" && git push
   ```
6. Done. You'll wake up in 15 minutes.

## Design Principles

- **Single file**: Everything stays in `taxclicker-pro.html`. No external dependencies except Google Fonts.
- **Kids first**: Simple language, bright colors, fun animations. No jargon.
- **Always playable**: Every commit must leave the game in a working state. Never break existing features.
- **Incremental**: Small, visible improvements each cycle. Not big rewrites.
- **Visual**: Kids love seeing things happen. Add animations, emojis, visual feedback.
- **Educational**: Sneak in concepts like "taxes pay for roads and schools" naturally through gameplay.

## SimCity Features to Add (priority order)

1. **Town Grid**: A visual grid (8x8 or 10x10) where buildings appear as you progress
2. **Building Types**: Houses (generate citizens), Shops (generate income), Schools (boost efficiency), Parks (boost happiness)
3. **Tax Rate Slider**: Kids set the tax rate. Too high = citizens leave. Too low = no money for services.
4. **City Services**: Roads connect buildings, fire station prevents disasters, hospital keeps citizens healthy
5. **Visual Growth**: Buildings start small and grow. Tiny pixel art or emoji-based graphics.
6. **Random Events**: "A new family moved to town!", "Storm damaged a building!", "Festival boosted happiness!"
7. **Happiness Meter**: Citizens' happiness affects tax revenue and growth
8. **Milestones**: "Village" -> "Town" -> "City" -> "Metropolis" as population grows
9. **Mini Budget Screen**: Simple income vs expenses visualization

## Keep the Windows 98 Aesthetic

The retro Windows 98 look is charming and unique. Keep the title bar, menu bar, tab system, and general styling. The SimCity grid should feel like it's running inside this retro window.

## Technical Notes

- All state in a single JS object (the existing `state` pattern)
- Use CSS Grid for the town layout
- Emoji or simple CSS shapes for buildings (no image assets)
- requestAnimationFrame or setInterval for game loop (already exists)
- Keep file under 5000 lines -- if it gets too big, simplify

## Game Rules

- **Win condition**: Reach $1 billion profit OR survive 30 minutes (whichever comes first)
- **30-minute timer**: Visible countdown. Game ends at 30 min with a score summary.
- **Scoreboard**: Show a scoreboard/leaderboard at the START of the game (before play begins). Store top scores in localStorage. Show player name, score, time, town size.
- **Score = total profit at end** (whether by hitting $1B or time running out)

## BUGS TO FIX (URGENT — fix these FIRST before any new features)

1. **Buy buttons don't work**: The "Buy[0]" buttons on the Upgrades/Staff/Clients tabs do nothing when clicked, even when the player has enough money (cost shows green). The purchase function is broken. Fix the onclick handler so buying actually works.

2. **Countdown timer too small**: Make the 30-minute countdown clock LARGE and always visible in a corner of the screen (e.g. top-right). It should be easy to see at a glance — big font, bold, maybe with a background.

## What NOT to Change

- Don't remove the Windows 98 aesthetic
- Don't add external JS libraries (keep it self-contained)
- Don't make it too complex -- a 6-year-old should be able to click around and have fun
- Don't add features that require reading paragraphs of text
