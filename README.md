# Staff Tug of War

A team competition for music class. Two players answer note names on the same large touchscreen **at the same time**, each correct answer pulling the rope one notch their way. Win by dragging it over the line, or by leading when time runs out.

Staff Tug of War is part of **Dato Music Lab** (https://datomusiclab.dpdns.org), a working elementary music teacher's studio in Taipei.

## What it is

Sight-reading practice is usually silent and private, which makes it invisible to everyone except the child doing it. Turning it into a rope the whole class can watch changes what the room does during the drill.

The design problem was simultaneity. Most two-player web games take turns, or use one global lock so the faster player eats the other's tap. Here both halves of the screen track their own touch points independently, so two students can press at the same instant — or one team can hammer their side — and every press registers.

## Features

**Genuinely simultaneous input.** Pointer Events, with the left and right zones tracking their own touches and no global lock anywhere. Nothing gets swallowed.

**Notation done properly.** Clefs embed Bravura's original outlines — the SMuFL standard music font — rather than depending on a system font. Anchoring follows the SMuFL specification: the spiral of the G clef centres on the second line, and the two dots of the F clef straddle the fourth. Staff line weight, notehead proportions and ledger line lengths are all derived from SMuFL ratios, so nothing distorts when the display scales.

**Even question distribution.** Cards are dealt from a shuffled deck and the deck is only reshuffled once exhausted, so every note comes up and none is missed for an entire match.

**Wrong answers teach.** A miss flashes the correct answer long enough to register before moving on, and the end-of-match summary lists the notes this class got wrong most often — which is exactly the revision list for next lesson.

**Physically believable animation.** The tug is drawn from real mechanics: bodies lean back around 35 degrees, feet plant ahead of the body, rope passes across the hip. The scoring team hauls back and kicks up dust; the losing team is dragged forward, leaving scuff marks.

## How to use

Keep three files together — `index.html`, `cover.jpg`, `hoory.mp3` — and open `index.html`. Nothing to install; after the first load it runs with no network at all.

1. Press **Start** on the cover to play immediately, or **Choose your team** to open settings first
2. Use the fullscreen button, top left

### Settings

| Option | Choices |
|:---|:---|
| Clef | Treble / bass / mixed |
| Range | Within the staff only / including ledger lines |
| Match length | 1 / 2 / 3 / 5 minutes |
| Winning margin | 6 / 8 / 10 / 12 points |
| Answer button height | 0–36vh, to suit screen size and how tall the students are |
| Sound | Final ten-second countdown and victory cheer, mutable |
| Team names | Both teams |

Settings persist in the browser and carry over to the next lesson.

### In the classroom

- Two students at the screen, the rest of each team behind them reading the staff and calling advice
- Raise the answer button height for younger children so nobody has to stoop
- Start beginners on treble clef within the staff — nine notes — and add ledger lines once that is comfortable
- A 6-point winning margin makes short matches, so a single lesson can rotate through many pairs

## Tech

Native HTML, CSS and JavaScript. Zero frameworks, zero build step, zero external dependencies. Both the staff and the tug-of-war scene are SVG generated at runtime.

- Clef and notehead outlines come from [Bravura](https://github.com/steinbergmedia/bravura) (SIL Open Font License 1.1)
- Sound effects are synthesised with the Web Audio API and need no audio files

## License

Code is MIT — see [LICENSE](LICENSE). Artwork, audio and the embedded font have separate terms; see [NOTICE.md](NOTICE.md).

## More from Dato Music Lab

Reading notes is one half; producing them is the other — the studio also builds recorder games where a microphone listens to what the child actually plays and flies a plane or slices fruit accordingly. And for the ear rather than the eye, there is a detective game for spotting a single note bent sharp or flat. All at **https://datomusiclab.dpdns.org**.
