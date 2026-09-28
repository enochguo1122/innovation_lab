# innovation_lab
Here's some not-serious programs that might get your attention. I love to make my interesting ideas work. feel free to take them away and recreate these ideas yourself!

# Stickman Ping Pong
(inspired by "I'm ping pong king" in 2018 by Orangenose Studio)
(this whole purpose of the program is to remake "pingpong king" game, ive been wanting to play it and its so sad its been taken down form ios app store)

A minimalist table tennis game that runs in any modern browser, on desktop or mobile. You play as a stickman, and your goal is to read the spin on each incoming ball and return it with the right stroke, at the right time, on the right side.

**Play:** https://enochguo1122.github.io/innovation_lab/

The whole game is a single `index.html` file, with no dependencies, no build step, and no audio or image assets.

## How to play

| Input | Touch | Keyboard |
|---|---|---|
| Flat hit | Tap the left or right half of the screen | A / D or ← / → |
| Topspin | Swipe up | Q / E |
| Backspin | Swipe down | Z / C |

- **Side:** choose the side of the screen where the ball is arriving.
- **Timing:** hit early to send the ball cross-court, or hit late to send it down the line. Hitting exactly on time sends it through the middle. Placement follows a continuous curve rather than fixed zones.
- **Spin:** read the incoming spin from the ball's trail color. Red is topspin, blue is backspin, and purple is sidespin.
  - Flat hits against topspin go long.
  - Flat hits against backspin go into the net.
  - Backspin strokes against topspin pop up and go long.
  - Topspin strokes against very heavy backspin can also hit the net unless the timing is perfect.
- **Rating:** well-timed hits are rated PERFECT or GOOD. Better hits are faster and put more pressure on the AI.

## Modes

- **Match to 11:** standard scoring. The serve changes every 2 points, then every point from 10–10, and you must win by 2. There are four difficulty levels, each with a different spin set, ball speed, and AI rally stamina.
- **Practice:** endless rallies against an AI that never misses. The difficulty rises as your streak grows, and your best score is saved.

## Features

- Pseudo-3D ball physics, including height, shadows, and table bounces.
- A spin model with Magnus curve in the air, spin-dependent bounce height, and post-bounce speed of ×1.2 for topspin, ×0.8 for backspin, and ×1.0 for sidespin.
- Stickmen that lunge to the ball, lean into their movement, and use different swing arcs for each stroke.
- An AI whose errors combine fatigue, which grows with rally length and depends on the level, and pressure, which depends on your shot quality and how far the AI has to run.
- Synthesized sound effects using the Web Audio API.
- English and Chinese interface.
- Safe-area support for iPhone. The game can be added to the home screen for a near full-screen experience.

## AI contribution

This project was built through a collaboration between the author and **Claude**, an AI assistant made by Anthropic.

**Author (enochguo1122)**
- Provided the initial prototype: a stickman ping pong game with left/right tap controls.
- Set the product direction and requested features: player movement, spin physics, sound, match and practice modes, and bilingual UI.
- Acted as game designer: defined the difficulty tiers, the timing-based placement mechanic, bounce speed ratios, and pacing goals for rally length.
- Gave UI and UX feedback, which led to a simplified interface with collapsible help and level info.
- Playtested on iOS and reported issues.

**Claude (AI)**
- Wrote most of the code in its current form, including:
  - the physics engine and shot planner;
  - the spin and "reading spin" rules;
  - the AI opponent and difficulty system;
  - gesture input and timing judgment;
  - audio synthesis, localization, and UI.
- Proposed design options for discussion, such as the fatigue and pressure model for AI errors and timing-based placement.
- Ran automated headless simulations to check shot validity and balance rally lengths across difficulty levels.

All design decisions were made by the author. Claude implemented them and suggested options.

## License

Personal project. Add a license here if you plan to share or reuse the code.
