# Picture Skill · Pen & Watercolor Travel Journal

[简体中文](README.md) · [Skill instructions](skills/pen-watercolor-travel-journal-v1-0/SKILL.md) · [MIT license](LICENSE)

Redraw a supplied photo as a gentle pen-and-light-watercolor travel journal illustration. Preserve the subject, spatial relationships, and aspect ratio; let the painting fade naturally into the paper; add handwritten English lettering and four flat color swatches sampled from the photo.

This repository contains an **Agent Skill instruction package**. It does not include an image model, API keys, or a standalone drawing application. You must supply a photo and use an AI host with image-editing capabilities. Installing the skill alone does not provide those capabilities.

## Example · Sunlit Cosmos

![Sunlit Cosmos pen-and-watercolor travel journal example](examples/pen-watercolor-travel-journal/01-sunlit-cosmos/result.jpg)

A finished example supplied by the user: orange and yellow flowers, a soft green background, handwritten English lettering, and four color swatches. Only the supplied example image is included; the corresponding source photo is not available in this repository.

[Example notes](examples/pen-watercolor-travel-journal/01-sunlit-cosmos/README.md) · [View example image](examples/pen-watercolor-travel-journal/01-sunlit-cosmos/result.jpg)

## Visual style

| Element | Drawing requirement |
| --- | --- |
| Scene fidelity | Preserve the main subjects, relative positions, perspective, orientation, and original aspect ratio |
| Pen linework | Fine, light, broken lines for essential contours, with less detail in the background |
| Watercolor | Low-saturation transparent washes, subtle paper texture, and natural pigment marks |
| Continuous paper | Let the scene fade into the paper and bottom lettering space, without frames or collage panels |
| Adaptive background | Choose a paper wash based on the photo's light, temperature, and day or night atmosphere |
| English lettering | One title and one short subtitle in natural handwriting |
| Four swatches | Exactly four small rounded-square, flat-color swatches at the bottom right, all derived from the photo |

Suitable subjects include travel, streets, architecture, landscapes, gardens, and everyday scenes. See [SKILL.md](skills/pen-watercolor-travel-journal-v1-0/SKILL.md) for the full constraints and review workflow. These are the skill's intended requirements; results depend on the host and image-editing tool.

## Installation

### Use Skill Installer in Codex

In a Codex environment that provides the built-in `skill-installer`, send:

```text
$skill-installer Install the skill at skills/pen-watercolor-travel-journal-v1-0 from https://github.com/LiyuTian-web/picture-skill.
```

Check the skill list after installation. Restart Codex if the skill does not appear. The installer adds the instruction package; the host must still provide image-editing tools.

### Manual installation

1. Download this repository as a ZIP, or clone it:

   ```sh
   git clone https://github.com/LiyuTian-web/picture-skill.git
   ```

2. Copy the **entire** `skills/pen-watercolor-travel-journal-v1-0` folder into your target project's `.agents/skills/` directory.
3. Confirm that the resulting path is `.agents/skills/pen-watercolor-travel-journal-v1-0/SKILL.md`.
4. Open Codex in the target project and check that it discovers the skill. Restart Codex if needed.

These steps describe a project-local installation in Codex. For other hosts supporting Agent Skills, follow their import instructions and verify support for photo input and image editing. This repository has not verified results in other hosts.

For installation and discovery behavior, see the [official OpenAI skills documentation](https://learn.chatgpt.com/docs/build-skills).

## Usage

Attach the photo you want to transform, then send a request such as the following. These are invocation examples, not generated-result demonstrations.

### Let the skill write the lettering

```text
Use $pen-watercolor-travel-journal-v1-0 to turn my uploaded photo into a pen-and-watercolor travel journal illustration.
Keep the original aspect ratio and main subjects, and write the lettering based on the scene.
```

### Supply exact English lettering

```text
Use $pen-watercolor-travel-journal-v1-0 to transform my uploaded photo.
Title: A Quiet Afternoon
Subtitle: A little light along the familiar road.
Keep both English lines exactly as written.
```

### Save the result

Explicitly ask to save the finished image and specify the destination. The skill requires a new filename to avoid overwriting the original.

The default delivery is one finished image and a brief creative note of 1–3 sentences in Chinese. The full prompt, Scene Card, specific color values, and detailed composition notes are provided only when explicitly requested.

## Usage notes

- A reference photo is required. It is the editing target and the source of the palette.
- Without supplied lettering, the skill writes an English title and subtitle based on visible scene cues, without inventing specific locations, dates, or personal information.
- The skill requests the original aspect ratio. If the host cannot match it exactly, it should report the actual output dimensions.
- Check English spelling, scene fidelity, and the number of swatches. An explicit failure allows at most one targeted correction.
- Source photos are not part of this repository. The skill instructs the host not to search for supplementary photos or upload photos to unspecified destinations, and not to write images into the project unless requested or required for delivery by the host.

## Repository structure

```text
picture-skill/
├── README.md
├── README.en.md
├── LICENSE
├── .gitignore
├── .gitattributes
├── examples/
│   └── pen-watercolor-travel-journal/
│       └── 01-sunlit-cosmos/
│           ├── README.md
│           └── result.jpg
└── skills/
    └── pen-watercolor-travel-journal-v1-0/
        └── SKILL.md
```

The included version is **v1.0**. Its skill identifier is `pen-watercolor-travel-journal-v1-0`. The skill instructions are written in Chinese, with an English frontmatter description.

## Feedback and license

Use [Issues](https://github.com/LiyuTian-web/picture-skill/issues) to report problems or suggest improvements. Describe your host environment, expected result, and observed differences. Do not submit API keys or photos you are not authorized to share.

The skill instructions and documentation in this repository are available under the [MIT license](LICENSE).
