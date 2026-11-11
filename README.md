# motion-ad-director

A Claude Code skill that interviews you and walks you through making a short motion-graphics /
SaaS / app / product ad: brief, assets, level choice, storyboard approval, build, then sound,
voiceover and music.

## Attribution

All of the methodology here comes from **Rourke Heath (RourkeIdeas)** and his video
[Claude Opus 5.5: How To Make Motion Graphics](https://www.youtube.com/watch?v=cDb-wPq0Iyk).
The build engine is his free `saas-animation` skill, available from
https://rourkeideas.com/downloads/claude-opus-motion-graphics . **It is not included in this
repo**; download it yourself from his page. This project is unofficial and not affiliated with
or endorsed by him. Mentions of tools and sound packs (ElevenLabs, Suno, Artlist, Oculus Sound,
Blender) come from his video and are not endorsements by this repo.

## What we did

1. Read the creator's download page and fetched the video's captions.
2. Pulled out the practical instructions he gave (paraphrased; the transcript is not published).
3. Turned them into a staged, interactive skill: it asks for anything missing, requires storyboard
   approval before building, does visuals before sound, and asks before spending paid credits.
4. Left the heavy lifting (templates, rendering, Blender scripts) to his `saas-animation` skill.

## The stages

0. Project folder -> 1. Brief -> 2. Ingredients (high-res logo, screenshots) -> 3. Level
(1 prompt-only, 2 brand art + AI voice/music, 3 Blender) -> 4. Numbered storyboard + approval ->
5. Build -> 6. Sound (after picture lock) -> 7. Deliver.

## Install

```bash
git clone https://github.com/emeraldhycient/motion-ad-director ~/.claude/skills/motion-ad-director
```

Then install `saas-animation` from the link above, and run `/motion-ad-director`.

## License

MIT for the original text in this repo. The video and the `saas-animation` skill belong to their creator.
