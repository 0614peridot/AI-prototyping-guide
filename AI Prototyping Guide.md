# AI Prototyping Guide for Product Designers

A short, practical guide for turning Figma ideas into working prototypes with AI.

## 1. AI Tools to Use

Use these tools together, not all at once.

| Tool | Best For |
| --- | --- |
| Codex | Building and editing real prototype code inside a project folder |
| Cursor | AI-assisted coding with a familiar editor |
| Claude | Planning flows, writing prompts, reviewing copy, reasoning through UX |
| ChatGPT | Brainstorming, writing specs, creating prompts, debugging ideas |
| Gemini | Research, multimodal feedback, Google ecosystem work |
| Spline | Creating interactive 3D scenes and exports |
| Omma | Interactive 3D design prototyping for spatial interfaces, motion, and product experiences |

Simple rule: use Figma for design source of truth, AI for building, and browser preview for checking the result.

## 2. Basic Concepts

**Prototype**  
A realistic version of an idea that people can click, test, and react to.

**AI prototyping**  
Using AI to create or edit a working prototype from your design, prompt, or product idea.

**Design tokens**  
Reusable design values such as colors, spacing, radius, fonts, and shadows.

**Component**  
A reusable UI piece, like a button, card, modal, nav bar, or input.

**MCP**  
A connection layer that lets AI tools talk to apps like Figma.

**Local project folder**  
The folder on your computer where the prototype files live.

## 3. How to Get Set Up

1. Install your AI coding tool: Codex or Cursor.
2. Create one folder for the prototype.
3. Add your design references: Figma link, screenshots, product notes, and design tokens.
4. Choose a simple frontend stack, usually React, Vite, and CSS or Tailwind.
5. Ask AI to create the first version.
6. Run the prototype locally.
7. Review it in the browser and ask AI to refine it.

Keep the first version small. Build one flow before building the whole product.

## 4. How to Connect Figma MCP

Figma MCP lets an AI tool inspect Figma designs more directly.

General setup:

1. Open your AI tool's MCP settings.
2. Add the Figma MCP server.
3. Connect your Figma account or token.
4. Give access to the target Figma file.
5. Paste the Figma file link into your AI tool.
6. Ask the AI to inspect the frame, components, variables, and styles.

Helpful prompt:

```text
Use the Figma MCP connection to inspect this file. Focus on the selected frame, design tokens, components, spacing, typography, and interaction states. Then summarize what you need before building the prototype.
```

What to check:

- The AI can see the correct file.
- The selected frame is the one you want.
- Tokens and components are named clearly.
- You are not asking it to build from an outdated frame.

## 5. AI Prototyping Workflow

Use this loop:

1. **Prepare**: clean up the Figma frame and name important layers.
2. **Describe**: explain the goal, audience, flow, and fidelity level.
3. **Generate**: ask AI to build the first prototype.
4. **Preview**: open it in the browser and click through it.
5. **Compare**: check visual match, spacing, states, and responsiveness.
6. **Refine**: give specific feedback, one batch at a time.
7. **Test**: share with teammates or users.
8. **Package**: document what is real, fake, clickable, or placeholder.

Good feedback sounds like:

```text
Make the prototype closer to the Figma frame. The header is too tall, the card spacing should be tighter, the primary button should use the brand blue token, and the mobile layout should stack the filters above the results.
```

## 6. Recommended Root Folder Structure

Use a simple structure:

```text
prototype-name/
  README.md
  package.json
  index.html
  src/
    App.jsx
    main.jsx
    styles.css
    components/
    data/
    assets/
  design/
    figma-link.md
    screenshots/
    tokens.json
  notes/
    prompts.md
    decisions.md
```

What goes where:

- `src/`: the working prototype
- `components/`: reusable UI pieces
- `data/`: fake data for the prototype
- `assets/`: images, icons, videos, Spline exports
- `design/`: Figma references and design tokens
- `notes/`: prompts, decisions, and feedback

## 7. Prompt Guide for Accurate Token-Based Prototypes

Use prompts that include goal, source, constraints, and expected output.

Starter prompt:

```text
Build a clickable prototype for product designers based on this Figma design.

Goal:
[Describe what the user should be able to do.]

Design source:
[Paste Figma link or describe the selected frame.]

Use these design tokens:
- Colors: [list tokens]
- Typography: [list fonts/sizes]
- Spacing: [list spacing scale]
- Radius: [list radius values]
- Shadows: [list shadow styles]

Requirements:
- Match the Figma layout closely.
- Use reusable components.
- Make it responsive for desktop and mobile.
- Use realistic sample data.
- Keep the code simple and easy to edit.

Before coding, summarize the design system and ask only if something is missing.
```

Refinement prompt:

```text
Compare the current prototype against the Figma design. Fix visual mismatches in spacing, typography, colors, radius, and component states. Keep the existing structure unless a change is needed for accuracy.
```

Interaction prompt:

```text
Add realistic interactions for this flow: [describe flow]. Include hover, selected, loading, empty, and error states where useful. Do not add extra screens unless needed.
```

## 8. How to Add a Spline Design

Use Spline when 3D helps explain the product, object, space, or motion.

Common options:

1. **Embed from Spline**
   - Publish the Spline scene.
   - Copy the embed URL.
   - Add it to the prototype with Spline's viewer package or an iframe.

2. **Export assets**
   - Export images, video, or 3D assets from Spline.
   - Place them in `src/assets/` or `public/`.
   - Use them like normal visual assets.

Prompt:

```text
Add this Spline scene to the prototype as the main interactive visual. Keep it responsive, make sure it does not cover the UI, and include a fallback image for slower devices.
Spline URL: [paste URL]
```

Good practice:

- Keep Spline scenes lightweight.
- Avoid putting important text inside the 3D scene.
- Test on laptop and mobile sizes.
- Use a static fallback if performance is slow.

## 9. Useful Tips

- Start with one user journey, not the whole product.
- Give AI screenshots, tokens, and the Figma link together.
- Ask for small changes instead of giant rewrites.
- Keep fake data realistic.
- Label what is clickable and what is static in your notes.
- Save strong prompts in `notes/prompts.md`.
- Use browser screenshots to compare before and after changes.
- Ask AI to make components reusable only after the direction is stable.
- Treat AI output as a draft. You are still the designer.

## Quick Checklist

Before sharing a prototype:

- The main flow works.
- The visual style matches the design direction.
- Buttons, forms, and navigation feel realistic.
- Mobile layout is not broken.
- Placeholder content is clearly intentional.
- The README explains how to run it.
- Known limitations are documented.

## One-Line Starting Prompt

```text
Help me turn this Figma design into a small, realistic, clickable prototype for product design review. Prioritize visual accuracy, simple code, responsive layout, and clear interaction states.
```
