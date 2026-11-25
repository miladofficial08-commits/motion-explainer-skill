# /motion-explainer

A free Claude Code skill. You type one idea, Claude builds a short explainer video (9:16) in code on your computer:
pictogram characters, thin line icons, word-by-word titles. No editor, no AI video model.

## Install

1. Copy the folder `skills/motion-explainer` into your `.claude/skills` folder.
2. Restart Claude Code.
3. Type `/motion-explainer` and your idea, for example: `/motion-explainer why we forget names in ten seconds`.

A finished 9-second example is in `skills/motion-explainer/template`.

## What you need

- Claude Code (paid Claude plan)
- Node.js, because the video is rendered with HyperFrames (`npx hyperframes`)

## What it does not do

It makes one video when you ask. It does not pick topics, add voices, check sound or post anything.

That part is AIMO Studio, the agent this skill comes from. It makes and schedules videos every day in four styles.
Our own agent has published over 40 videos; none were edited by hand.
https://aimo-community.netlify.app/?src=gh
