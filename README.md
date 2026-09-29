# innovation_lab
Here's some not-serious programs that might get your attention. I love to make my interesting ideas work. feel free to take them away and recreate these ideas yourself!

# Stickman Ping Pong
(inspired by "I'm ping pong king" in 2018 by Orangenose Studio)

A fast, minimalist table tennis game that runs in the browser on phones and desktops. Read the spin, pick your side, and time the hit to place the ball exactly where you want it. The goal is quick, satisfying rallies rather than slow strategy.

**Play:** https://enochguo1122.github.io/innovation_lab/

The whole game is a single `index.html` file, with no dependencies, no build step, and no image or audio assets. Everything is drawn on a canvas, and all sounds are synthesized.

## How to play

| Action | Touch | Keyboard |
|---|---|---|
| Flat hit | Tap the left or right half of the screen | A / D or ← / → |
| Topspin | Swipe up | Q / E |
| Backspin (chop) | Swipe down | Z / C |

- **Side:** tap the side of the screen where the ball is arriving.
- **Placement:** hit early to go cross-court, or hit late to go down the line, all the way to the sideline. A small aim marker on the opponent's side shows where the ball will land if you hit right now. Normal returns always land on the table.
- **Spin:** read the incoming spin from the ball.
  - Trail color: red is topspin, blue is backspin, and purple is sidespin.
  - Faster stripes and a darker trail mean heavy spin.
  - Topspin needs a topspin stroke, and backspin needs a chop.
  - The wrong stroke on light spin gives a weak return. On heavy spin, you lose the point.
- **Timing:** PERFECT and GOOD hits are faster and put more pressure on the opponent.

## Modes

- **Match to 11:** standard scoring. The serve changes every 2 points, then every point from 10–10, and you must win by 2. There are four difficulty levels, each with a different spin set, ball speed, and AI reaction time, running speed, and rally stamina.
- **Endless:** keep the rally going for as long as you can against an AI that never misses. The difficulty rises as your streak grows, and your best score is saved.

## Characters

| Character | Style | Special ability |
|---|---|---|
| **Classic** (black) | All-round | Reads spin and answers it with the right stroke. |
| **JOO** (blue) | Chopper | Swipe down to chop back any topspin as heavy backspin that curves outward. Heavy topspin slows down as it reaches him. Three PERFECT chops force the opponent into a high ball. |
| **WANG** (red) | Attacker | His topspin beats any spin, travels faster, and always counts as PERFECT. Rallies speed up the longer they last. |

## Highlights

- **Smash:** when the AI returns a high ball, the screen focuses on you and slows down.
  - The camera zooms in and the sound goes muffled while you wind up.
  - A clean hit triggers an impact frame and speed lines, and the ball explodes off the table.
  - In a match, a smash always wins the point. Consecutive smashes escalate the effects.
- **AI out of position (Match to 11):** the AI has a reaction delay and a top running speed. Move it from corner to corner, and if it can't reach your shot, the point is yours.
- **PERFECT combo:** a faint "PERFECT ×n" watermark sits behind the table and grows as your combo builds.
- **Game feel:**
  - ball squash on every hit and bounce;
  - point celebrations;
  - a crowd that gets louder during long rallies;
  - a soft flash every 10 hits;
  - hit sounds that rise in pitch as your streak grows.
- **English and Chinese interface**, with a language toggle in the top-right corner.
- **iPhone-friendly:** add the game to your home screen for a near full-screen experience.

## AI contribution

This project was built through a collaboration between the author and **Claude**, an AI assistant made by Anthropic.

**Author (enochguo1122)**
- Provided the initial prototype: a stickman ping pong game with left/right tap controls.
- Led the game design:
  - the "fast and satisfying" direction;
  - difficulty levels;
  - timing-based placement;
  - bounce speed rules;
  - the JOO and WANG characters and their abilities;
  - the smash focus and slow-motion effect;
  - the Endless mode intro.
- Made UI and UX decisions, including the minimal interface, collapsible help, and language toggle.
- Playtested on iOS and reported issues, such as the combo reset bug.

**Claude (AI)**
- Wrote most of the code in its current form:
  - the physics engine and shot planner;
  - the spin rules;
  - the AI opponent;
  - gesture input and timing judgment;
  - characters;
  - visual effects;
  - synthesized audio;
  - localization and UI.
- Proposed design options for discussion, including:
  - the AI error model;
  - AI out of position;
  - visible spin strength;
  - the aim marker;
  - the combo watermark;
  - the smash effect sequence.
- Ran automated headless simulations and browser screenshots to check shot validity, balance, and layout.

The author made all design decisions. Claude implemented them and suggested options.

## License

Personal project. Add a license here if you plan to share or reuse the code.
