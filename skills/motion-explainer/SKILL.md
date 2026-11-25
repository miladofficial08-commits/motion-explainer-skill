---
name: motion-explainer
description: Makes a minimal motion-explainer short (9:16) with pictogram characters, thin line icons and word-by-word titles on a dark background with a violet glow. Built in code with HyperFrames, one idea per video. Use when the user runs /motion-explainer or asks for a minimal explainer, a pictogram explainer, a "the kid who..." style short, or an explainer with stick-pictogram people and line icons.
---

# /motion-explainer

A calm, minimal explainer: one idea, told in short beats. Each beat is one sentence at the top and one simple
picture below it. A finished 9-second example is in `template/` ("The kid who doodles in class").

## The look

- **Ground:** near-black (`#06050c`) with one soft violet glow behind the picture. Nothing else in the background.
- **People:** pictograms made of a circle and a rounded body. Everyone is white; the one person the story is about
  is violet (`#8f6bff`). Bystanders can be dimmed to 50 %.
- **Icons:** thin white lines (7 px, round caps), drawn in while the sentence is spoken. One icon per beat.
- **Titles:** top of the frame, bold capitals (Inter 900, about 84 px), arriving word by word with a short blur-in.
  One or two key words per sentence in violet (`#9d7bff`). No captions at the bottom.
- **Numbers:** one big number per video at most, counting up and landing with a small scale punch. Put the source
  in small grey type under the picture.
- **Small labels:** a thin outlined pill ("New story") or a red outlined stamp ("Not this") when a beat needs it.

## Pacing

- A new beat every 2 to 2.6 seconds. Each beat is its own scene: new sentence, new picture.
- Words arrive 0.18 to 0.26 s apart. The first word is on screen on the first frame.
- Lines draw in 0.6 to 1.2 s. Bars and people pop in with a short ease, never a slow fade.
- The glow drifts slowly for the whole video so no frame is fully still.

## Steps

1. **One idea.** Write the claim in one sentence. If it needs a number, find the source first and keep it.
2. **Beats.** Split it into 4 to 8 sentences of at most 6 words. Mark one or two key words per sentence.
3. **Pictures.** For each beat choose one picture: people in a row, one person with an icon, two bars, a line that
   becomes something. If a beat needs more than one picture, split the beat.
4. **Copy the template.** `cp -r <this skill>/template <project>`, then edit `index.html`: one `.scene` per beat with
   its `data-start` and `data-duration`, the words as `<span>`s in `.cap`, and the picture below.
5. **Animate.** Use the helpers in the template: `word(id, time)` for each word, `draw(pathId, time, seconds)` for
   lines. Keep every time a plain number in seconds.
6. **Check.** `npx hyperframes check`, then `npx hyperframes snapshot --at <one time per beat>` and look at the stills:
   no title over the picture, nothing below 1330 px that must be read, key words in violet.
7. **Voice (optional).** With a voiceover, take the word times from it and set each `word()` to its spoken time.
8. **Render.** `npx hyperframes render -o <name>.mp4` (1080 x 1920, 30 fps).

## Rules

- One idea per video, one picture per beat, one accent colour.
- Every number has a source on screen. No invented results.
- Learn the pattern from other creators, never copy their script, characters or frames.
- Keep text inside the area between 170 px and 1330 px from the top; the app covers the rest.
