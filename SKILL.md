---
name: motion-ad-director
description: Guided, step-by-step workflow for making a short motion-graphics / SaaS / app / product ad with Claude. Interviews the user for everything it needs (product, length, assets, ending, level, sound), enforces storyboard-first approval, then hands the build to the saas-animation skill and finishes with sound design, voiceover and music. Use when someone says "make an ad / promo / motion graphic / app video / product video", or invokes /motion-ad-director.
---

# Motion ad director

Based on the workflow taught by Rourke Heath (RourkeIdeas) in "Claude Opus 5.5: How To Make
Motion Graphics" (https://www.youtube.com/watch?v=cDb-wPq0Iyk). This skill is the guided
checklist; the build engine is his free `saas-animation` skill. Check it is installed
(`~/.claude/skills/saas-animation`). If not, tell the user to download it from
https://rourkeideas.com/downloads/claude-opus-motion-graphics and stop until it is.

Ask questions in small batches (max 4 at a time), skip anything the user already answered,
and never invent assets. Work in one folder per video.

## Stage 0: Project folder
Confirm or create a folder for this video (e.g. `Spotify-ad/`). Everything goes in it:
assets, storyboard, renders, audio.

## Stage 1: Brief (ask for what is missing)
- Product/brand, audience, where it will be seen
- Length (15s, 30s, or other). Fixes the storyboard AND voiceover/music length later
- Call to action / ending (App Store, website, sign-up, or a cut into real footage)
- Voiceover? Custom music? Sound effects?

## Stage 2: Ingredients: quality in = quality out
Ask for and verify:
1. **High-resolution logo** (never crop a logo from a screenshot; never redraw it from shapes
   unless the user explicitly agrees and checks it)
2. **UI screenshots** of the app, brand colours, fonts, existing illustrations
3. **Physical products:** reference of every angle, and ideally the real product on hand
4. Optional: user's own AI images/video, a sound-effects pack, a music file
Check resolutions; ask for better assets rather than proceeding with weak ones.

## Stage 3: Choose a level
| Level | Adds | Needs |
|---|---|---|
| 1 | Pure prompting in Claude: clean app/UI ads | assets only |
| 2 | Brand art (puppet-animated cutouts), AI voiceover, custom music | ElevenLabs connector, Suno (optional) |
| 3 | Blender: realistic lighting for physical products | Blender installed (never opened by user) |

Recommend a level from the brief. Level 3 only for physical products / studio-lit looks.
For level 2 voiceover ask whether the ElevenLabs connector is connected. For level 3 check
Blender is installed (`which blender` / /Applications/Blender.app).

## Stage 4: Numbered storyboard: STOP for approval
Create a numbered storyboard (5-10 shots, time ranges, what is on screen, what moves, how
each shot becomes the next). Bake in these directing rules:
- **Every shot transforms into the next.** No cross-dissolves. Ask "how does this shape become
  that shape?" for each transition.
- **Keep the focus dead-centre**, effects happen around it.
- **Always some motion**: camera move or moving elements, never a static hold.
- **Shallow depth of field** and varied camera movement for a cinematic look.
- **Text:** no bouncing, no letter-fades; each word slides up in place, one after another.
- **Ending** designed backwards from the call to action. If cutting into footage, end exactly
  on the user's reference frame.
- Blender level: a single motivated key light rather than light everywhere.

Show it, take notes, revise, and do NOT build until the user clearly says approved.
Notes are not approval. Changed shots/order/transitions need re-approval.

## Stage 5: Build (visuals only)
Hand to the `saas-animation` skill with the approved storyboard, assets and level. Expect
roughly 8-12 minutes for a simple ad. Review stills/contact sheets as a motion designer.
Physical product: ask the user to compare the render against the real product (shape, parts
passing through each other, left/right) and fix differences. Iterate notes until the picture
is approved. Keep versions; never delete user files.

## Stage 6: Sound, only after the picture is locked
Changing visuals later breaks sound sync.
1. **Sound effects:** use packs in the project folder (suggest a paid pack or a subscription
   library such as Artlist; the source video used Oculus Sound). Place them on the beats.
2. **Voiceover (level 2+):** with the final length known, write a script that fits each shot,
   then generate it via the ElevenLabs connector. **Ask before spending credits.**
3. **Music:** write a Suno prompt for a track of the exact video length. The user generates it
   (ask first if automated), then mix in and set volumes.

## Stage 7: Deliver
Final export plus a summary of what was made, versions, and what was not checked (stills are
not playback; audio cannot be heard by Claude). Offer another round of notes.

## Rules
- Generic short prompts give generic output: push for artistic direction.
- Paid services: always confirm first.
- Never claim something was checked if it was not.
